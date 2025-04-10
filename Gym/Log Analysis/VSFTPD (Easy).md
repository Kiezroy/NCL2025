Analyze a VSFTPD log file that we obtained.

[vsftpd.log](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015dbad4ea5fef1fceaa6/65b02e00ad4ea5fef1fd1da0/65b02e00ad4ea5fef1fd1da2/download?t=3)


Q1 - 5 points

What IP address did "ftpuser" first log in from?

![](attachments/Pasted%20image%2020250330172205.png)

`10.0.0.123`

Q2 - 5 points

What is the first directory that ftpuser created?

![](attachments/Pasted%20image%2020250330172234.png)

`TreeSizeFree`

Q3 - 5 points

What is the last directory that ftpuser created?

![](attachments/Pasted%20image%2020250330172319.png)

`110D300S`

Q4 - 10 points

What file extension was the most used by ftpuser?

````
cat vsftpd.log | grep ftpuser | grep 'OK UPLOAD' | awk -F ',' '{print  $2 }' | cut -d '"' -f 2 | awk -F "." '{print $NF }' | sort | uniq -c
````

![](attachments/Pasted%20image%2020250330172601.png)

`JPG`


Q5 - 10 points

What is the username of the other user in this log?

```
root@DESKTOP:~# cat vsftpd.log | grep '\[.*\] \[.*\]' | awk -F ' ' '{print $8}' | sort | uniq

[ftpuser]
[jimmy]
```


`jimmy`

Q6 - 10 points

What IP address did this other user log in from?

```
root@DESKTOP:~# cat vsftpd.log | grep jimmy
Sat Mar 19 18:24:08 2016 [pid 1923] [jimmy] OK MKDIR: Client "10.0.0.214", "/home/jimmy/BBall Pics"
Sat Mar 19 18:24:08 2016 [pid 1927] [jimmy] OK LOGIN: Client "10.0.0.214"
Sat Mar 19 18:24:08 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/DSC_8227.JPG", 5797085 bytes, 108527.26Kbyte/sec
Sat Mar 19 18:24:08 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/DSC_8228.JPG", 6165401 bytes, 109598.43Kbyte/sec
Sat Mar 19 18:24:08 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/DSC_8229.JPG", 6521273 bytes, 104209.17Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0146.JPG", 6427078 bytes, 111406.93Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0148.JPG", 5376676 bytes, 110451.85Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0223.JPG", 6403167 bytes, 106786.43Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0245.JPG", 7193680 bytes, 109771.99Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0299.JPG", 6379095 bytes, 107640.48Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0300.JPG", 6829094 bytes, 107709.31Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0372.JPG", 6962334 bytes, 111487.13Kbyte/sec
```

`10.0.0.214`

Q7 - 10 points

How many total bytes did this other user upload?

````
cat vsftpd.log | grep jimmy | grep 'OK UPLOAD' | awk -F ',' '{print  $3 }' | cut -f 2 -d ' ' | awk '{s+=$1} END {printf "%.0f\n", s}'
````

`105750628`

Q8 - 10 points

How many total bytes did ftpuser upload?

```
cat vsftpd.log | grep ftpuser | grep 'OK UPLOAD' | awk -F ',' '{print  $3 }' | cut -f 2 -d ' ' | awk '{s+=$1} END {printf "%.0f\n", s}'

```

`13980839165`

Q9 - 10 points

How many total bytes did ftpuser download?

```
cat vsftpd.log | grep ftpuser | grep 'OK DOWNLOAD' | awk -F ',' '{print  $3 }' | cut -f 2 -d ' ' | awk '{s+=$1} END {printf "%.0f\n", s}'
```


`6008032`

Q10 - 25 points

Identify the IP address of the suspicious login (the login with no subsequent activity)

- Find all the IPs in the log
- Search each one for it's activity
- Find the one that had no activity

```
root@DESKTOP:~# cat vsftpd.log | grep 'OK LOGIN' | awk -F '"' '{print $2 }' | sort | uniq
10.0.0.123
10.0.0.214
10.3.0.6

root@DESKTOP:~# cat vsftpd.log | grep 10.0.0.214
Sat Mar 19 18:24:08 2016 [pid 1923] CONNECT: Client "10.0.0.214"
Sat Mar 19 18:24:08 2016 [pid 1923] [jimmy] OK MKDIR: Client "10.0.0.214", "/home/jimmy/BBall Pics"
Sat Mar 19 18:24:08 2016 [pid 1928] CONNECT: Client "10.0.0.214"
Sat Mar 19 18:24:08 2016 [pid 1927] [jimmy] OK LOGIN: Client "10.0.0.214"
Sat Mar 19 18:24:08 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/DSC_8227.JPG", 5797085 bytes, 108527.26Kbyte/sec
Sat Mar 19 18:24:08 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/DSC_8228.JPG", 6165401 bytes, 109598.43Kbyte/sec
Sat Mar 19 18:24:08 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/DSC_8229.JPG", 6521273 bytes, 104209.17Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0146.JPG", 6427078 bytes, 111406.93Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0148.JPG", 5376676 bytes, 110451.85Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0223.JPG", 6403167 bytes, 106786.43Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0245.JPG", 7193680 bytes, 109771.99Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0299.JPG", 6379095 bytes, 107640.48Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0300.JPG", 6829094 bytes, 107709.31Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0372.JPG", 6962334 bytes, 111487.13Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0373.JPG", 7047407 bytes, 108691.44Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0378.JPG", 6558648 bytes, 110693.20Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0696.JPG", 7064902 bytes, 110542.97Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0739.JPG", 6788203 bytes, 111207.93Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0772.JPG", 7122209 bytes, 110578.58Kbyte/sec
Sat Mar 19 18:24:09 2016 [pid 1842] [jimmy] OK UPLOAD: Client "10.0.0.214", "/home/jimmy/BBall Pics/_DSC0894.JPG", 7114376 bytes, 109892.65Kbyte/sec
Sat Mar 19 18:24:45 2016 [pid 1842] [jimmy] OK MKDIR: Client "10.0.0.214", "/home/jimmy/basketball"
Sat Mar 19 18:24:45 2016 [pid 1842] [jimmy] OK MKDIR: Client "10.0.0.214", "/home/jimmy/basketball/Good"

root@DESKTOP:~# cat vsftpd.log | grep 10.3.0.6
Sat Mar 19 18:24:47 2016 [pid 1853] [ftpuser] OK UPLOAD: Client "10.0.0.123", "/home/ftpuser/basketball/DSC_8154.JPG", 5912154 bytes, 108330.60Kbyte/sec
Sat Mar 19 18:24:59 2016 [pid 1853] [ftpuser] OK UPLOAD: Client "10.0.0.123", "/home/ftpuser/basketball/DSC_8308.JPG", 6181516 bytes, 104360.64Kbyte/sec
Sat Mar 19 18:35:48 2016 [pid 2485] CONNECT: Client "10.3.0.6"
Sat Mar 19 18:35:49 2016 [pid 2484] [ftpuser] OK LOGIN: Client "10.3.0.6"
root@DESKTOP:~#
```


`10.3.0.6`
