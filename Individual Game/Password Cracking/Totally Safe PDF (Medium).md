
Our analysts retrieved this encrypted PDF from a Liber8tion FTP server. Decrypt it and uncover its contents.

[secure.pdf](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860df0/6727d986b9452dcac540ecbf/67d822d77c06227c4a515c5c/67f04470eeed046aeded82f2/download?t=3)

- Use pdf2john tool

Q1 - 25 points  
What is the password to open the PDF file?

```
┌──(kali㉿kali)-[~/Downloads]
└─$ pdf2john secure.pdf > secure_pdf.hash


┌──(kali㉿kali)-[~/Downloads]
└─$ john secure_pdf.hash --wordlist=/usr/share/wordlists/rockyou.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (PDF [MD5 SHA2 RC4/AES 32/64])
Cost 1 (revision) is 2 for all loaded hashes
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
pdfscott86       (secure.pdf)     
1g 0:00:00:01 DONE (2025-04-13 14:42) 0.8928g/s 4240Kp/s 4240Kc/s 4240KC/s pdgtengku..pdeb?
Use the "--show --format=PDF" options to display all of the cracked passwords reliably
Session completed. 

```

`pdfscott86`

Q2 - 25 points  
What is the flag?

![](../../attachments/Pasted%20image%2020250413114341.png)

`SKY-PDFS-2472`