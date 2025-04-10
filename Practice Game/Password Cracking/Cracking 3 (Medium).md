
We have obtained password dumps storing hacker passwords. It appears that they are all in the format: "SKY-SENH-" followed by 4 digits. Can you crack them?

- Identify hashes as `md5` with hashid or hash-identifier

- Use hashcat
	- -a 3 (specifies brute force mode)
	- ?d (specifies a digit to brute force)

| User                                                                                                      | Password Ciphertext              | Command                                                                                                                      | Answer        |
| --------------------------------------------------------------------------------------------------------- | -------------------------------- | ---------------------------------------------------------------------------------------------------------------------------- | ------------- |
| #### ![](https://assets.cyberskyline.com/img/avatars/small/daniel.jpg?t=3)<br><br>Daniel<br><br>15 points | 7bd5a56b969c70453de13e143d426b77 | `hashcat -a 3 -m 0 "7bd5a56b969c70453de13e143d426b77" SKY-SENH-?d?d?d?d`![image](attachments/Pasted-image-20250403221457.png) | SKY-SENH-5494 |
| #### ![](https://assets.cyberskyline.com/img/avatars/small/mark.png?t=3)<br><br>Mark<br><br>15 points     | d594609bce40643b168f308acea31755 | `hashcat -a 3 -m 0 "d594609bce40643b168f308acea31755" SKY-SENH-?d?d?d?d`![image](attachments/Pasted-image-20250403221651.png) | SKY-SENH-1137 |
| #### ![](https://assets.cyberskyline.com/img/avatars/small/ade.jpg?t=3)<br><br>Ade<br><br>15 points       | eeb52a806d1c88733d5ce6c0d93ed4b7 | `hashcat -a 3 -m 0 "eeb52a806d1c88733d5ce6c0d93ed4b7" SKY-SENH-?d?d?d?d`![image](attachments/Pasted-image-20250403221804.png) | SKY-SENH-1100 |
|                                                                                                           |                                  |                                                                                                                              |               |
