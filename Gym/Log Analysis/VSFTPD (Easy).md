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

Q8 - 10 points

How many total bytes did ftpuser upload?

Answer...

Q9 - 10 points

How many total bytes did ftpuser download?

Answer...

Q10 - 25 points

Identify the IP address of the suspicious login (the login with no subsequent activity)