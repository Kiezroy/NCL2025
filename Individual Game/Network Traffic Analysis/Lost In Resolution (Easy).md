
You've been provided with a pcap file containing network traffic. Your task is to analyze the traffic to uncover key details about the user's activity and identify a hidden flag.

[traffic.pcapng](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860df0/67d81da97c06227c4a5153f3/67d822567c06227c4a515b24/67db0511b6fe5a213d33f7a4/download?t=3)

Q1 - 10 points  
What is the transaction ID for the DNS query for frame 36?

- Go to frame 36
- Domain Name System (query) > Transaction ID

![](../../attachments/Pasted%20image%2020250412075701.png)

`0x75b8`

Q2 - 10 points  
What is the email provider they use?

- Query wireshark to filter for the word mail
- `frame contains "mail"`



`protonmail.com`

Q3 - 20 points  
In frame 10061, what is the second A record returned for the domain chatgpt.com?



Q4 - 20 points  
What is the transaction ID for the first query to pwn.college?



Q5 - 20 points  
What is the flag contained in the DNS A and AAAA record for the domain, flag.com.localdomain?



Q6 - 20 points  
What is the average DNS payload size? (in bytes, rounded to 2 decimal points)