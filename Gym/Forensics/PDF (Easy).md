Our analysts managed to get hold of a document that we believe has a flag on it. Can you recover it?

[api.pdf](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015b9ad4ea5fef1fce971/65b02e0aad4ea5fef1fd20b0/65b02e0aad4ea5fef1fd20b2/download?t=3)

Q1 - 15 points

What is the name of the program that exported this PDF file?

- Use exiftool

	![](attachments/Pasted%20image%2020250330155544.png)

`Adobe Photoshop`

Q2 - 15 points

What PDF version is this file?

`exiftool api.pdf | grep -i version`

`PDF Version                     : 1.7`

Q3 - 20 points

What software was used to redact the file and insert a watermark?

- Use online metadata viewer

	![](attachments/Pasted%20image%2020250330160255.png)

`PDFTron`

Q4 - 50 points

What is the flag?

- Look at the TextLayer area
	![](attachments/Pasted%20image%2020250330160334.png)

`SKY-PDRD-2390`