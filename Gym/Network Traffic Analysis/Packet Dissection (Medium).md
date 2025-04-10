
Dissect an IP packet header to understand how the protocol works.

![](../../attachments/Pasted%20image%2020250409224312.png)


<img src="attachments/Pasted%20image%2020250409224330.png" width="1200">

![attachments/Pasted image 20250410115218.png](../../attachments/Pasted%20image%2020250410115218.png)



Q1 - 20 points  
What is the header checksum in hexadecimal representation?

- Check where the Header Checksum is located
- Its at columns 16-31 at row 3 (64 bits)

![[../../attachments/Pasted image 20250410124638.png|Pasted image 20250410124638.png]]

![attachments/Pasted image 20250410121600.png](../../attachments/Pasted%20image%2020250410121600.png)

`4f 93`


Q2 - 20 points  
What is the TTL of the packet?

- Row 3, line 1 (1st 8 bits or 1 byte)

![attachments/Pasted image 20250410122246.png](../../attachments/Pasted%20image%2020250410122246.png)

![attachments/Pasted image 20250410122425.png](../../attachments/Pasted%20image%2020250410122425.png)

`64`

Q3 - 30 points  
What is the source IP address?

![Pasted image 20250410122645.png](../../attachments/Pasted%20image%2020250410122645.png)

![[../../attachments/Pasted image 20250410123943.png|Pasted image 20250410123943.png]]

`192.168.128.128`

Q4 - 30 points  
What is the destination IP address?

![[../../attachments/Pasted image 20250410124810.png|Pasted image 20250410124810.png]]

![[../../attachments/Pasted image 20250410124845.png|Pasted image 20250410124845.png]]

`159.203.96.154`
