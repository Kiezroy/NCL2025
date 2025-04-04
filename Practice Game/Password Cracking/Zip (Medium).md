
We have captured an encrypted archive from a hacker's FTP server. Decrypt it and find out what you can.

[Encrypted.zip](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860ded/67e5b9ed660b44323954ad16/605cd06922195c5bcbb0d58f/605cd08822195c5bcbb0d590/download?t=3)

What is the password used to encrypt the zip archive? (15 pts)

- Use zip2john to get the hash of the zip file

```
┌──(kali㉿kali)-[~/Downloads]
└─$ zip2john Encrypted.zip > encryptedhash.txt
ver 1.0 Encrypted.zip/zip_archive/ is not encrypted, or stored with non-handled compression type
ver 1.0 efh 5455 efh 7875 Encrypted.zip/zip_archive/flag.txt PKZIP Encr: 2b chk, TS_chk, cmplen=26, decmplen=14, crc=E52C5B2C ts=704D cs=704d type=0

```

- Use john with wordlist rockyou.txt to crack hash

