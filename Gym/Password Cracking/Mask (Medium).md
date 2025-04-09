
Our analysts have obtained password dumps storing hacker passwords. After obtaining a few plaintext passwords, it appears that they are all in the format: `SKY-HQNT-` followed by 4 digits. Can you crack them?

- Identify the hashes as MD5
- Use hashcat with brute force enabled for digits

Example:

```
┌──(kali㉿kali)-[~]
└─$ hashcat -m 0 -a 3 "71b816fe0b7b763d889ecc227eab400a" SKY-HQNT-?d?d?d?d
```

Can also do multiple cracks at once by putting in one file

```
┌──(kali㉿kali)-[~]
└─$ hashcat -m 0 -a 3 hashes.txt SKY-HQNT-?d?d?d?d 

...

06f03267f31077d2c4b5c728472070ae:SKY-HQNT-6598            
d866f4b3b34b598375149fb7661113ab:SKY-HQNT-5981            
d9053951a8d1c15254b46ec9fc974a6b:SKY-HQNT-9816  
```

| User                                                                                                 | Password Ciphertext              | Answer          |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- | --------------- |
| ![](https://assets.cyberskyline.com/img/avatars/small/helen.jpg?t=3)<br><br>Helen<br><br>20 points   | 71b816fe0b7b763d889ecc227eab400a | `SKY-HQNT-8765` |
| ![](https://assets.cyberskyline.com/img/avatars/small/stevie.jpg?t=3)<br><br>Stevie<br><br>20 points | 674291170dffcf620bda2a604a6820ea | `SKY-HQNT-2984` |
| ![](https://assets.cyberskyline.com/img/avatars/small/chris.jpg?t=3)<br><br>Chris<br><br>20 points   | 06f03267f31077d2c4b5c728472070ae | `SKY-HQNT-6598` |
| ![](https://assets.cyberskyline.com/img/avatars/small/tom.jpg?t=3)<br><br>Tom<br><br>20 points       | d866f4b3b34b598375149fb7661113ab | `SKY-HQNT-5981` |
|  ![](https://assets.cyberskyline.com/img/avatars/small/mark.png?t=3)<br><br>Mark<br><br>20 points    | d9053951a8d1c15254b46ec9fc974a6b | `SKY-HQNT-9816` |
