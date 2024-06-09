
> #### BASICS
- Authentication (e.g: Prove your indentity by showing password)
- Authorization  (e.g: Prove you are allowed to onboard flight by showing boarding-pass)

> #### PKI BASICS
- Asymetric Encryption Algorithms / Protocols
  - RSA (Used for Encryption, KeyExchange, Signature)
  - Diffe Helmen ( Used only for KeyExchange )
  - Digital Signatures ( Used only for signing )
 
> #### OpenSSL Commands
- Read contents of the certificate
  - openssl x509 -in google.cert -noout -text
- Read contents of the private key
  - openssl rsa -in google.key -noout -text
- Read contents of the certificate using domainname
  - openssl s_client google.com:443
- Fetch SAN List & supress unwanted lines
  - openssl s_client -connect google.com:443 -servername google.com < /dev/null 2>/dev/null | openssl x509 -noout -ext subjectAltName | grep -vE "depth|verify return|X509"
    
> #### Secure WEB API
- :point_right: [ API ](https://www.mulesoft.com/resources/api/what-is-an-api)
- Secure Communication
  - Confidentiality – Assuring only the intended recipients in communication have access to the message.
    - Solution: Encryption/Decryption ( Requires Shared Key ) 
  - Integrity – Assuring that the message cannot be modified in transit without the other party being made aware.
    - Solution: Hashing Algorithms (MD5/SHA1/SHA2) ( Requires Shared Key )
  - Authentication – Assuring the other party is indeed who they claim to be.
    - Solution: PKI
  - Anti-Replay – Assuring the message cannot be maliciously re-transmitted.
- Secure API Development Techniques:
  - JSON Web Tokens (JWT) should be used for API client authentication and authorization.
  - Access Control policies should be written to limit write access and access to sensitive data.
  - Role based access should be implemented to limit administrative access to resources.
  - Rate-limit threshold should be set to limit the number of requests from a specified source.
  - HTTPS should be used to encrypt the request & response between the client and API.
- :point_right:[ auth0 ](https://auth0.com/docs/videos/learn-identity-series)
