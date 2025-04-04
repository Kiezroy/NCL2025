
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

```
┌──(kali㉿kali)-[~/Downloads]
└─$ john encryptedhash.txt --wordlist=/usr/share/wordlists/rockyou.txt 
Using default input encoding: UTF-8
Loaded 1 password hash (PKZIP [32/64])
Will run 4 OpenMP threads
Press 'q' or Ctrl-C to abort, almost any other key for status
hammonds13       (Encrypted.zip/zip_archive/flag.txt)     
1g 0:00:00:00 DONE (2025-04-04 01:21) 1.754g/s 13523Kp/s 13523Kc/s 13523KC/s hanbuger..hallnoates
Use the "--show" option to display all of the cracked passwords reliably
Session completed. 

```

`hammonds13`

What is the flag hidden in the zip archive? (15 pts)

-

```
┌──(kali㉿kali)-[~/Downloads]
└─$ unzip Encrypted.zip                                               
Archive:  Encrypted.zip
[Encrypted.zip] zip_archive/flag.txt password: 
 extracting: zip_archive/flag.txt    

```