Analyze a git project and find some hidden flags. You can try to clone the repository with this link: git@gitlab.com:cybergit4823/my-awesome-flag-project.git but that might not work for you. If not, you'll need to find a way around it.

- Tried to `git clone` the repository which didn't work

```
root@DESKTOP:~# git clone git@gitlab:cybergit4823/my-awesome-flag-project.git
Cloning into 'my-awesome-flag-project'...
ssh: Could not resolve hostname gitlab: Name or service not known
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
```


"To access it via the browser, you can restructure the URL as a web URL which will generally have the convention of `https://[hostname]/[username]/[repository name]`"

- So I went to https://gitlab.com/cybergit4823/my-awesome-flag-project.git which worked!


Q1 - 10 points

What is the display name of the author of this git project?

![](attachments/Pasted%20image%2020250330211758.png)

`Cyber Cyber`

Q2 - 10 points

What is the short commit hash (first 8 characters) of the initial commit?

![](attachments/Pasted%20image%2020250330211849.png)

`f9714edd`

Q3 - 15 points

What is flag #1?

![](attachments/Pasted%20image%2020250330211906.png)

`SKY-HSNO-2303`

Q4 - 15 points

What is flag #2?

- Explore the branches and go to the flag2 branch
- Find flag2.txt

![](attachments/Pasted%20image%2020250330211956.png)

`SKY-OZNW-3730`

Q5 - 15 points

What is flag #3?

- Right on the project page

![](attachments/Pasted%20image%2020250330212037.png)

`SKY-CCXL-4067`

Q6 - 15 points

What is flag #4?

- Go to past commits and find the flag

![](attachments/Pasted%20image%2020250330212156.png)

`SKY-IRRK-9672`

Q7 - 20 points

What is flag #5?

- Go to the commit of removing 