
Investigators have uncovered password dumps from the servers of the Liber8tion criminal group. Another team found that the rockyou wordlist was effective in cracking similar passwords. Will you be able to break them?

- Use hashcat to crack

For Joe:

```
┌──(kali㉿kali)-[~]
└─$ hashcat -m 0 "7f40b66512418322f2e6ea309a749c18" /usr/share/wordlists/rockyou.txt    

7f40b66512418322f2e6ea309a749c18:queen11 
```

| User                                                                                                       | Password Ciphertext              | Answer  |
| ---------------------------------------------------------------------------------------------------------- | -------------------------------- | ------- |
| ![](https://assets.cyberskyline.com/img/avatars/small/joe.jpg?t=3)<br><br>Joe<br><br>10 points             | 7f40b66512418322f2e6ea309a749c18 | queen11 |
| ![](https://assets.cyberskyline.com/img/avatars/small/christian.jpg?t=3)<br><br>Christian<br><br>20 points | 7073fb2108940c1933eaa43c2a3df1d8 |         |
| ![](https://assets.cyberskyline.com/img/avatars/small/nom.jpg?t=3)<br><br>Nom<br><br>20 points             | 6976b8c351e9c2bb5bf72cc4c83cba4e |         |