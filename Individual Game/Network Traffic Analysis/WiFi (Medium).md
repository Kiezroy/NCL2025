
A wireless network was compromised by liber8tion. Analyze the packet capture and figure out what happened.


Q1 - 20 points  
What is the MAC address of the router?

- Look at the source address for TpLinkTechno

![](../../attachments/Pasted%20image%2020250413094746.png)

`c0:4a:00:80:76:e4`

Q2 - 20 points  
What is the ESSID of the router?

- Open a packet > IEE 802.11 Wireless Management > Tagged Parameters > Tag: SSID parameter set

![](../../attachments/Pasted%20image%2020250413095629.png)

`Wii Fii`

Q3 - 20 points  
What is the MAC address of the victim that was deauthenticated from the WiFi network?

- Find the packet where the deauthentication starts
- Source address > MS-NLB-PhysServer-32_18

![](../../attachments/Pasted%20image%2020250413095838.png)

`02:38:aa:ae:9f:e6`

Q4 - 20 points  
What channel is the WiFi network running on?

- Find a packet after the deauthentication ones
- IEEE 802.11 Wireless Management > Tagged parameters > Tag: DS Parameter set: Current Channel : 4

![](../../attachments/Pasted%20image%2020250413101525.png)

`4`

Q5 - 20 points  
What is the password for the WiFi network?

- Use aircrack-ng with wordlist rockyou.txt to crack the password

