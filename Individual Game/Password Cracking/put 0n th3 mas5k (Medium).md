
Our analysts have uncovered password dumps from the servers of the Liber8tion criminal group. All the passwords follow a curious pattern: **SKY-MASK-????**. Can you uncover the missing pieces?

- First identify the hash type

![](../../attachments/Pasted%20image%2020250413114727.png)

- Looks like its most likely md5crypt, so use the hashcat tool to crack it



| User                                                                                                       | Password Ciphertext            | Answer |
| ---------------------------------------------------------------------------------------------------------- | ------------------------------ | ------ |
| ![](https://assets.cyberskyline.com/img/avatars/small/nan.jpg?t=3)<br><br>Nan<br><br>10 points             | $1$MASK$F4TXNX..S3nYzItvwpywa. |        |
| ![](https://assets.cyberskyline.com/img/avatars/small/christian.jpg?t=3)<br><br>Christian<br><br>20 points | $1$MASK$6GNQLeQG65VI6xusDOMnf0 |        |
|  ![](https://assets.cyberskyline.com/img/avatars/small/nom.jpg?t=3)<br><br>Nom<br><br>20 points            | $1$MASK$DnjCzEUFZGK/O.4YOGcDw/ |        |