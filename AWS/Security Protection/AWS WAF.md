# AWS Web Application Firewall

#### Keypoints
- The AWS WAF (Web Application Firewall) service is designed to operate at Layer 7 of the OSI Model. It performs stateful inspection on specific web application endpoints, allowing users to analyze and control web traffic at a more granular level.
- With AWS WAF, users can choose to allow, block, or count requests based on various criteria such as request content or source IP. It offers flexibility in filtering and modifying requests, providing enhanced protection for web applications.
- Enabling sampled requests in AWS WAF allows users to visualize a subset of incoming requests without incurring the additional cost of enabling logging. It provides a way to get insights into the nature and frequency of requests that are being processed by the web ACL. This feature can be useful for monitoring and understanding the overall traffic patterns and potential threats without the need for extensive logging.
- The services that support WAF web ACLs include CloudFront distributions (for global scope web ACLs), API Gateway endpoints, Application Load Balancers (at Layer 7), and AppSync (for GraphQL APIs). These integrations allow users to enforce security rules and mitigate web-based attacks on their applications deployed in AWS.

<img width="613" alt="image" src="https://github.com/cskarthik22/Notes/assets/38231831/bd29ed26-9e30-42cc-b940-f712dce20356">
