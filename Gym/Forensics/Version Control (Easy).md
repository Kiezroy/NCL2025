One of our employee's computer was compromised and we saw this backup file leave the network, but we couldn't find anything other than a simple README.md file in it. Help us found out what information the hackers got.

[git_backup.zip](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015b9ad4ea5fef1fce971/65b015b9ad4ea5fef1fce975/65b015b9ad4ea5fef1fce977/download?t=3)

**Cyber Command**

What is the email address of the employee who was compromised? (10 pts)

- Look at the logs folder and find the email

	![](attachments/Pasted%20image%2020250330153525.png)

`gpeterson@mpd.hacknet.cityinthe.cloud`


Each employee is assigned a flag. What is the flag that was compromised? (20 pts)

- Unzip the git_backup.zip and find the commit hash
- `git show` the hash for the flag

	![](attachments/Pasted%20image%2020250330154652.png)
	
	![](attachments/Pasted%20image%2020250330154702.png)
	
	![](attachments/Pasted%20image%2020250330154730.png)

`-SKY-LRHX-4910`


Greg thinks that he may have had additional account credentials that were compromised. What's the name of the service provider for that other compromised account? (15 pts)

- Explore the other branches and look around for interesting items

```
root@DESKTOP:~/git_backup# git branch
* master
  next
root@DESKTOP:~/git_backup# git checkout next
Switched to branch 'next'
root@DESKTOP:~/git_backup# ls
README.md  passwords.txt
root@DESKTOP:~/git_backup# cat README.md
This repo is for storing important information
root@DESKTOP:~/git_backup# cat passwords.txt
Facebook: waffles85
root@DESKTOP:~/git_backup#

```

`Facebook`

What was the password on that compromised account? (15 pts)

`waffles85`