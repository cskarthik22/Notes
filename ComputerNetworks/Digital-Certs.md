https://www.youtube.com/watch?v=qXLD2UHq2vk&feature=youtu.be

VPN: https://www.youtube.com/watch?v=4BfL0UHrzDY

Scenario: https://google.com

Security philosophy - Two different models to send traffic from LAN ( Organization ) to WAN (Internet ).
- Blacklisting : Default is to ALLOW all outbound traffic by enabling ports (i.e: later, if needed block the selected ports) 
- Whitelisting ( Best Approach ) : Default is to BLOCK all outbound traffic by blocking ports (i.e later, enable only required 
  ports)

```diff

+   Internet --> Firewall --> Corportate-LAN ( Web Servers, DB Servers , Financial Servers ... etc )
   
+ DMZ Architecture:
!                       # ########################################################################################## 
!                       #                    +++++++++Organization's PRIVATE CORPORATE-LAN++++++++++++++
!                       #
!                       #    |% F %|                               |% F %|
!                       #    |% I %|                               |% I %| 
!                       #    |% R %|    |----------------|         |% R %|
!                       #    |% E %|    |  ( DMZ NTW )   |         |% E %| 
!PUBLIC ------>Internet # -->|% - %|--->|  Web Servers   |-------> |% - %|----->( DB Servers, Financial Servers )
!               (ISP)   #    |% W %|    |                |         |% W %| 
!                       #    |% A %|    |________________|         |% A %|
!                       #    |% L %|                               |% L %|
!                       #    |% L %|                               |% L %|
!                       #
!                       #
!                       #############################################################################################
```
