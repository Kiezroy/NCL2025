
There appears to be a flag inside this file, can you extract it and find out some more information about this archive file?

[secrets.tar.gz](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860ded/67e5b9ca660b44323954abee/624cb56eaf1f67858fef5422/624cb88baf1f67858fef585b/download?t=3)

- Unzip the file using `tar -xzvf secrets.tar.gz`


Q1 - 10 points

How many files are present inside the archive?

```
root@DESKTOP:~# tar -xzvf secrets.tar.gz
secrets/
secrets/note.txt
secrets/flag.txt
```

`2`

Q2 - 20 points

What is the flag?

```
root@DESKTOP:~# cd secrets/
root@DESKTOP:~/secrets# ls
flag.txt  note.txt
root@DESKTOP:~/secrets# cat flag.txt
SKY-LRDA-9420
```


`SKY-LRDA-9420`

Q3 - 30 points

What is the name of the user that created the flag file?

`tar -tvf secrets.tar.gz`

`-t` is list
`-v` is verbose
`-f` is filename

```
root@DESKTOP:~# tar -tvf secrets.tar.gz
drwxrwxr-x skye/skye         0 2022-04-05 14:35 secrets/
-rw-r--r-- liber8tion/liber8tion 20 2022-04-05 14:35 secrets/note.txt
-rw-rw-r-- skye/skye             32 2022-01-02 07:07 secrets/flag.txt
```

`skye`

Q4 - 40 points

When was the flag file created? (in UTC)

