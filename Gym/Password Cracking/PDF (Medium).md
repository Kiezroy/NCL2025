
We have captured an encrypted pdf from a hacker's FTP server. Decrypt it and find out what you can.

[encrypted.pdf](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015a1ad4ea5fef1fce6f4/65b02dfcad4ea5fef1fd1c53/65b02dfcad4ea5fef1fd1c55/download?t=3)

What is the password used to encrypt the pdf? (25 pts)

- Use pdf2john to create the hash of the encrypted file

```
┌──(kali㉿kali)-[~/Downloads]
└─$ pdf2john encrypted.pdf > pdf.txt
```

- Run