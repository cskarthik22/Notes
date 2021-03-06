
## Pods Scheduling

- ####   Scheduling New Pods Manually
```diff
##   Pod_Manual_Scheduling

+|   apiVersion: v1
+|   kind: Pod
+|   metadata:
+|     name: nginx
!|     namespace: dev
+|     labels:
+|       app: nginx
+|   spec:
+|     containers:
+|     - name: nginx
+|       image: nginx
-|       ports:
-|       - containerPort: 8080  
#|     nodeName: node-01
#|     schedulerName: default-scheduler

```

- #### Scheduling Existing Pods Manually
```diff
##   Manual_Scheduling Existing Pods

+|   apiVersion: v1
+|   kind: Binding
+|   metadata:
+|     name: nginx
+|   target:
+|     apiVersion: v1
+|     kind: Node
+|     name: node-02

!|   curl --header "Content-Type:application/json" 
!|        --request POST 
!|        --data '{"apiVersion":"v1", "kind": "Binding" ... }
!|        http://$IP/api/v1/namespaces/default/pods/$PODNAME/binding/

```

- ####   Taint => Node
```diff

+| kubectl taint nodes node-name key=value:taint-effect

!| taint-effect => ( NoSchedule, PreferNoSchedule, NoExecute )

Example:
+| kubectl taint nodes node-01 app=blue:NoSchedule

```

- ####   Tolerations => Pod
```diff
+|   apiVersion: v1
+|   kind: Pod
+|   metadata:
+|     name: nginx
!|     namespace: dev
+|     labels:
+|       app: nginx
+|   spec:
+|     containers:
+|     - name: nginx
+|       image: nginx
-|     tolerations:
-|     - key: "app"
-|       operator: "Equal"
-|       value: "blue"
-|       effect: "NoSchedule"

```

- ####   NodeSelector

```diff

#|  kubectl label nodes <node-name> <label-key>=<label-value> 
Example:

+|  kubectl label nodes node-01 size=Large

+|   apiVersion: v1
+|   kind: Pod
+|   metadata:
+|     name: nginx
!|     namespace: dev
+|     labels:
+|       app: nginx
+|   spec:
+|     containers:
+|     - name: nginx
+|       image: nginx
-|     nodeSelector:
-|       size: Large

!| Limitations: Uses single Label & selector, wont support multiple labels
+| %Solution%: Node Affinity

```

- ####   Node Affinity

```diff

#|  kubectl label nodes <node-name> <label-key>=<label-value> 
#|  Scenarios: How pods are scheduled, executed when,
#|     a) Nodes are Labelled vs Nodes are not labelled vs labels modified    

+|  kubectl label nodes node-01 size=Large
+|  kubectl label nodes node-02 size=Medium
+|  kubectl label nodes node-03 size=Small
-----------------------------------------------------------
+|   apiVersion: v1
+|   kind: Pod
+|   metadata:
+|     name: nginx
!|     namespace: dev
+|     labels:
+|       app: nginx
+|   spec:
+|     containers:
+|     - name: nginx
+|       image: nginx
-|     affinity:
-|       nodeAffinity:
-|         requiredDuringSchedulingIgnoreDuringExecution:
-|           nodeSelectorTerms:
-|           - matchExpressions:
-|             - Key: size
-|               operator: In
-|               values: 
-|               - Large
-|               - Medium
```

```
operator: IN, NotIn, Exists
Types: requiredDuringSchedulingIgnoreDuringExecution 
       preferredDuringSchedulingIgnoreDuringExecution
       requiredDuringSchedulingRequiredDuringExecution
```
