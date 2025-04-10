
The S in HTTPS stands for secure and it uses the TLS/SSL protocol to achieve its security. Let's decrypt this traffic to find the hidden flag.

[sslkeylog.log](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015f0ad4ea5fef1fced67/65b02dfead4ea5fef1fd1ce9/65b02dfead4ea5fef1fd1ceb/download?t=3)

[Decrypt.pcapng](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015f0ad4ea5fef1fced67/65b02dfead4ea5fef1fd1ce9/65b02dfead4ea5fef1fd1ced/download?t=3)


- Start wireshark
- Navigate to Edit > Preferences > TLS > Insert ssl key log

Q1 - 25 points

What Cipher Suite was chosen by the secure socket server?

- Packet 6 > Transport Security Layer > Handshake Protocol: Server Hello > Cipher Suite

![](Pasted%20image%2020250409223740.png)

`TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256`

Q2 - 25 points

What is the domain covered by the SSL key?

- Packet 6 > TLSv1.2 Record Layer: Handshake Protocol: Certificate > Certificates > Certificate > subject > rdnSequence

![](attachments/Pasted%20image%2020250409223930.png)

`tomsvacations.com`

Q3 - 50 points

What is the flag transferred over HTTPS?

- Right click packet > Follow TLS Stream

![](Pasted%20image%2020250409224214.png)

`SKY-LADN-1435`
