
  - AWS VPC         On_Premise       Public          IGW (Internet GW)
  - AWS VPC         On_Premise       Private         VPGW (Virtual Private GW )


- AWS Site to Site VPN ( Only sses IPSEC VPN Tunnel )
- AWS Client to Site VPN ( Uses OpenVPN Tunnel ) : By Default, client route table is overwritten by openvpn route table. Both local route table and OpenVPN route tables can be maintained by AWS Client VPN split tunneling
- Software VPN / EC2-VPN


Cloud Trail - doesnt see network traffic, it is an AWS API auditing service
