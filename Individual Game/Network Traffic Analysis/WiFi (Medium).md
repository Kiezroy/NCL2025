
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

- Use [aircrack-ng](https://www.aircrack-ng.org/) with wordlist rockyou.txt to crack the password

```
┌──(kali㉿kali)-[~/Downloads]
└─$ aircrack-ng wifi.cap -w /usr/share/wordlists/rockyou.txt 
Reading packets, please wait...
Opening wifi.cap
Read 477 packets.

   #  BSSID              ESSID                     Encryption

   1  C0:4A:00:80:76:E4  Wii Fii                   WPA (1 handshake)

Choosing first network as target.

Reading packets, please wait...
Opening wifi.cap
Read 477 packets.

1 potential targets



                               Aircrack-ng 1.7 

      [00:00:01] 4916/10303727 keys tested (5907.63 k/s) 

      Time left: 29 minutes, 3 seconds                           0.05%

                           KEY FOUND! [ soccer17 ]


      Master Key     : 91 AC F9 F0 77 57 DC 57 CE 95 2B 42 7E B8 19 E2 
                       E0 5D E6 1A 10 E5 01 39 7C 05 AB BF D7 16 5E 2C 

      Transient Key  : 91 87 84 42 C0 36 B5 A9 06 0D AD 07 F8 86 5B 3C 
                       56 EF 99 6E DD 5B 9D 00 00 00 00 00 00 00 00 00 
                       00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 
                       00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 00 

      EAPOL HMAC     : 05 92 EC 80 92 5A 7E 6C 11 6A 37 62 20 10 00 40 

```

`soccer17`