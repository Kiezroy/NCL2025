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

Answer...

Q6 - 10 points

What IP address did this other user log in from?

Answer...

Q7 - 10 points

How many total bytes did this other user upload?

Answer...

Q8 - 10 points

How many total bytes did ftpuser upload?

Answer...

Q9 - 10 points

How many total bytes did ftpuser download?

Answer...

Q10 - 25 points

Identify the IP address of the suspicious login (the login with no subsequent activity)