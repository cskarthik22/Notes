
#### Setup basic authentication on kubernetes ( kubeadm )

```diff
Edit the static pod 

apiVersion: v1
kind: Pod
metadata:
  name: kube-apiserver
  namespace: kube-system
spec:
  containers:
  - command:
    - kube-apiserver
    - --authorization-mode=Node,RBAC
      <content-hidden>
-   - --basic-auth-file=/tmp/users/user-details.csv
```
## Digital Certs

> Root CA certificate ( ca.crt )
```diff
+ ROOT CA
#1 Generate Keys 
   openssl genrsa -out ca.key 2048
#2 Request Certificate Signing Request
   openssl req -new -key ca.key -subj "/CN=Kubernetes-ca" -out ca.csr
#3 Sign Certificate ( self sign )
   openssl x509 -req -in ca.csr -signkey ca.key -out ca.crt
   
#4 View the certificate
   openssl x509 -in ca.crt -text -noout
```

> Client Certificates
```diff
+ KUBE-ADMIN
#1 Generate Keys 
   openssl genrsa -out admin.key 2048
#2 Request Certificate Signing Request
   openssl req -new -key admin.key -subj "/CN=Kube-admin/O=system:masters" -out admin.csr
#3 Sign with root ca Certificate 
   openssl x509 -req -in admin.csr -CA ca.crt -CAkey ca.key -CAcreateserial -out admin.crt
+ KUBE-SHCEDULAR

+ KUBE-CONTROLLER

+ KUBE-PROXY
   
```
> Server Certificates

## AUTHENTICATION - Request new admin cert
```
openssl genrsa -out admin-dev.key 2048
openssl req -new -key admin-dev.key -subj="/CN=admin-dev" -out admin-dev.csr

vi admin-dev-csr.yml

apiVersion: certificates.k8s.io/v1beta1
kind: CertificateSigningRequest
metadata:
  name: admin-dev
spec:
  groups:
  - system:authenticated
  usages: 
  - digital signature
  - key encipherment
  - server auth
  request:
    <<<< cat admin-dev.csr | base64 >>>>
```
```
kubectl get csr
kubectl certificate approve admin-dev
kubectl get csr admin-dev -o yaml

**Note: ALL certificate related operations ( csr approving & signing ) are carried-out by kubernetes-controller manager.
example: cat /etc/kubernetes/manifests/kube-controller-manager.yml
the below 2 entries are responsible for approving & signing
 --cluster-signing-cert-file=/etc/kubernetes/pki/ca.crt
 --cluster-signing-key-file=/etc/kubernetes/pki/ca.key
```
## AUTHORIZATION
```
vi my-role.yml

apiVersion: rbac.authorization.k8s.io/v1
kind: Role
metadata:
  name: developer
rules:
- apiGroups: [""]
  resources: ["pods"]
  verbs: ["list", "get", "create", "update", "delete"]
```
```
vi my-role-binding.yml

apiVersion: rbac.authorization.k8s.io/v1
kind: RoleBinding
metadata:
  name: developer-binding
subjects:
- kind: User
  name: admin-dev
  apiGroup: rbac.authorization.k8s.io/v1
roleRef:
  kind: Role
  name: developer
  apiGroup: rbac.authorization.k8s.io/v1
```
```
kubectl create -f my-role.yml
kubectl create -f my-role-binding.yml

kubectl get roles
kubectl get rolebindings
kubectl describe role developer
kubectl api-resources
```

## CLuster Role Binding
```
vi my-cluster-role.yml

apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRole
metadata:
  name: admin-cluster-role
rules:
- apiGroups: [""]
  resources: ["persistentvolumes"]
  verbs: ["list", "get", "create", "watch", "delete"]
- apiGroups: ["storage.k8s.io"]
  resources: ["storageclasses"]
  verbs: ["list", "get", "create", "watch", "delete"]
  
vi my-clusterrole-binding.yml

apiVersion: rbac.authorization.k8s.io/v1
kind: ClusterRoleBinding
metadata:
  name: admin-cluster-role-binding
subjects:
- kind: User
  name: admin-dev
  apiGroup: rbac.authorization.k8s.io/v1
roleRef:
  kind: ClusterRole
  name: admin-cluster-role
  apiGroup: rbac.authorization.k8s.io/v1

```

```
kubectl api-resources
kubectl create -f my-cluster-role.yml
kubectl create -f my-cluster-role-binding.yml

kubectl get clusterroles
kubectl get clusterrolebindings
```

## CHECK Resource access
```
kubectl auth can-i create deployments
kubectl auth can-i delete nodes
kubectl auth can-i delete nodes --as admin-dev
```
## Kube-Config

```diff
  apiVersion: v1
  kind: Config
  current-context: my-admin-dev@my-cluster-dev
+ clusters:
    - name: my-cluster-dev
      cluster: 
        certificate-authority: ca.crt
        server: https://my-cluster-dev:6443
    - name: my-cluster-test
      cluster: 
!       certificate-authority-data: <<<< cat ca.crt | base64 >>>>
        server: https://my-cluster-test:6443
+ context:
    - name: my-admin-dev@my-cluster-dev
      context:
        cluster: my-cluster-dev
        user: my-admin-dev
        namespace: dev-project-01
    - name: my-admin-test@my-cluster-test
      context:
        cluster: my-cluster-test
        user: my-admin-test
        namespace: test-project-01
+ users:
    - name: my-admin-dev
      user:
        client-certificate: admin-dev.crt
        client-key: admin-dev.key
    - name: my-admin-test
      user:
        client-certificate: admin-test.crt
        client-key: admin-test.key
```
```diff
!| default location: vi ~/.kube/config

kubectl config view
kubectl config use-context my-admin-test@my-cluster-test
kubectl config -h

```
## Docker private registry & securing images

```
STEP1: Setup private registry 
a) docker login <<<< privateregistry_url >>>>
b) kubectl create secret docker-registry my-reg-cred \
   -- docker-server= <<<< privateregistry_url >>>>
   -- docker-username= <<<< loginusername >>>>
   -- docker-password= <<<< loginpwd >>>>
   -- docker-email= <<< emailid >>>>

STEP2: Create a pod using image present in the private registry

vi my-nginx-pod.yml

apiVersion: v1
kind: Pod
metadata: 
  name: nginx-pod
spec:
  containers:
  - name: nginx
    image: <<<< privateregistry_url >>>>/imagename:latest
  imagePullSecrets:
  - name: my-reg-cred
   
```
