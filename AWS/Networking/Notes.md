

---

- AWS Site to Site VPN : Logical connection between AWS VPC and on-premise network encrypted using IPSec running over the public internet.
  -  VPN Connection between VGW (Virtual Private Gateway) and CGW (Customer Gateway)
  -  2 IPSec tunnels
  -  2 reslient publish space endpoints
  -  With Public Internet -> we see inconsistent performace

- Accelerted AWS Site to Site VPN:
  - AWS network has been extended closer to on-premise customers through Global accelerated edge locations
  - Not supported by VGW VPN
  - Supported by only TGW VPN (Transit Gateway)
  - 
