
We have captured an encrypted pdf from a hacker's FTP server. Decrypt it and find out what you can.

[encrypted.pdf](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015a1ad4ea5fef1fce6f4/65b02dfcad4ea5fef1fd1c53/65b02dfcad4ea5fef1fd1c55/download?t=3)

What is the password used to encrypt the pdf? (25 pts)

- Use pdf2john to create the hash of the encrypted file

```
┌──(kali㉿kali)-[~/Downloads]
└─$ pdf2john encrypted.pdf > pdf.txt
```

- Run john with the rockyou.txt wordlist

```
┌──(kali㉿kali)-[~/Downloads]
└─$ john --wordlist=/usr/share/wordlists/rockyou.txt pdf.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (PDF [MD5 SHA2 RC4/AES 32/64])
Cost 1 (revision) is 6 for all loaded hashes
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
0g 0:00:25:08 31.00% (ETA: 00:29:09) 0g/s 3051p/s 3051c/s 3051C/s podge75..poderosa77
0g 0:00:25:19 31.23% (ETA: 00:29:08) 0g/s 3051p/s 3051c/s 3051C/s pitchfo2..pitch05
keanureeves2008  (encrypted.pdf)     
1g 0:00:36:32 DONE (2025-04-08 23:44) 0.000456g/s 3039p/s 3039c/s 3039C/s keanurey1..keanu14
Use the "--show --format=PDF" options to display all of the cracked passwords reliably
Session completed. 

```

`keanureeves2008`

What is the flag in the PDF? (25 pts)

![](Pasted%20image%2020250408205127.png)

`SKY-KANU-5902`