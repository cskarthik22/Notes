
> #### Secure WEB API
- :point_right: [ API ](https://www.mulesoft.com/resources/api/what-is-an-api)
- Secure Communication
  - Confidentiality – Assuring only the intended recipients in communication have access to the message.
    - Solution: Encryption/Decryption
  - Integrity – Assuring that the message cannot be modified in transit without the other party being made aware.
    - Solution: Hashing Algorithms (MD5/SHA1/SHA2)
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
