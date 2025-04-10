Telnet is an older protocol that allowed an interactive text-oriented communication with remote systems, use the provided capture to answer the following questions about telnet.

[Telnet.pcap](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015f0ad4ea5fef1fced67/65b015f4ad4ea5fef1fceeee/65b015f4ad4ea5fef1fceef0/download?t=3)

Q1 - 10 points

What is the username that was used to log in?

- Go through the telnet packets and assemble the username

![](attachments/Pasted%20image%2020250330202401.png)

![](attachments/Pasted%20image%2020250330202411.png)

![](attachments/Pasted%20image%2020250330202431.png)

![](attachments/Pasted%20image%2020250330202443.png)

- Continue this to get `test`

Q2 - 10 points

What is the password that was used to log in?

- Follow the same method as Q1

![](attachments/Pasted%20image%2020250330202551.png)

- Eventually will get `capture`

Q3 - 20 points

What command was executed once the user was authenticated?

- Find this bash command `$`
- Follow the telnet to see what it will say

![](attachments/Pasted%20image%2020250330202720.png)

![](attachments/Pasted%20image%2020250330202727.png)

![](attachments/Pasted%20image%2020250330202737.png)

- Continue this pattern to get `uname -a`


Q4 - 20 points

In what year was this capture created?

![](attachments/Pasted%20image%2020250330203737.png)

`2011`

Q5 - 20 points

What is the hostname of the machine that was logged in to?

`cm4116`

Q6 - 20 points

What CPU architecture does the remote machine use?

`armv4tl`
