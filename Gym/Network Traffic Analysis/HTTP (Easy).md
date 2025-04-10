HTTP is how we're sending you this message, analyze the provided capture to answer the following questions about a HTTP download.

You can read this guide to learn more about computer networking.

[HTTP2.pcap](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015f0ad4ea5fef1fced67/65b015f3ad4ea5fef1fcee83/65b015f3ad4ea5fef1fcee85/download?t=3)

Q1 - 20 points

What Linux tool was used to execute a file download?

![image](attachments/Pasted-image-20250330191320.png)

`wget`

Q2 - 20 points

What is the name of the web server software that handled the request?

- Apply the http.response filter

	![image](attachments/Pasted-image-20250330192144.png)

`nginx`

Q3 - 20 points

What IP address initiated request?

![image](attachments/Pasted-image-20250330192225.png)

`192.168.1.140`

Q4 - 20 points

What is the IP address of the server?

![image](attachments/Pasted-image-20250330201311.png)

`174.143.213.184`

Q5 - 20 points

What is the md5sum of the file downloaded?

- Open in wireshark
- File > Export As > HTTP
- ![image](attachments/Pasted-image-20250330201909.png)
- Calculate the md5sum

```
root@DESKTOP:~# md5sum logo.png
966007c476e0c200fba8b28b250a6379  logo.png
```

`966007c476e0c200fba8b28b250a6379`
