
We've identified a packet capture with some potentially corrupt data. Analyze the pcap and answer the following questions

[checksum.pcap](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860ded/67e5b9d9660b44323954ac7e/6058f42c8e96845bcd2ff859/605d190e8e96845bcd300156/download?t=3)



Q1 - 10 points

What was the full domain name queried in the DNS request?

![](attachments/Pasted%20image%2020250403111735.png)

`use1-api.tplinkra.com`

Q2 - 10 points

What frame number contains an invalid IP checksum?

- Edit > Preferences > Protocols > IPv4 > Validate IPv4 checksum if possible

	![](attachments/Pasted%20image%2020250403112847.png)

-  Re-inspect the packets and find the one with a bad IP checksum

![](attachments/Pasted%20image%2020250403112924.png)

`64`

Q3 - 10 points

What frame number contains an invalid TCP checksum?

- Open in wireshark and inspect packets

![](attachments/Pasted%20image%2020250403112629.png)

`130`

Q4 - 10 points

What frame number contains an invalid UDP checksum?

- Follow same process as above to enable "Validate UDP checksum if possible"

	![](attachments/Pasted%20image%2020250403113020.png)

- Search through the packets

![](attachments/Pasted%20image%2020250403113048.png)

`53`

Q5 - 15 points

What is the name of the company that made the client device?

![](attachments/Pasted%20image%2020250403113157.png)

`TpLinkTechnologies`