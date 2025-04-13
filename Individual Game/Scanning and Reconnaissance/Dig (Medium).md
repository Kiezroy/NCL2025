
We've gained access to an internal DNS resolver that liber8tion has been using for their servers. Conduct a scan of the DNS records for liber8.cityinthe.cloud.

MAKE SURE TO USE THE DEVICE WITH THE resolver HOSTNAME IN THE PROVIDED TERMINAL AS YOUR DNS RESOLVER

- Use [`dig`](https://www.ibm.com/docs/pl/aix/7.1?topic=d-dig-command) command
- Refer to [DNS records](https://www.cloudflare.com/learning/dns/dns-records/)

Q1 - 10 points  
List one of the IPv4 addresses for `liber8.cityinthe.cloud`

`dig liber8.cityinthe.cloud @resolver`

- `@resolver` specifies the DNS server to look in

```
┌──(root㉿kali)-[~]
└─# dig liber8.cityinthe.cloud @resolver

; <<>> DiG 9.16.11-Debian <<>> liber8.cityinthe.cloud @resolver
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 27501
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;liber8.cityinthe.cloud.                IN      A

;; ANSWER SECTION:
liber8.cityinthe.cloud. 3600    IN      A       23.151.187.212
liber8.cityinthe.cloud. 3600    IN      A       43.71.247.55

;; Query time: 0 msec
;; SERVER: 10.7.71.132#53(10.7.71.132)
;; WHEN: Sun Apr 13 01:01:41 UTC 2025
;; MSG SIZE  rcvd: 83
```

`23.151.187.212`

Q2 - 15 points  
List one of the IPv6 addresses for `liber8.cityinthe.cloud`

- Query for DNS record `AAAA` for IPv6

```
┌──(root㉿kali)-[~]
└─# dig liber8.cityinthe.cloud @resolver AAAA

; <<>> DiG 9.16.11-Debian <<>> liber8.cityinthe.cloud @resolver AAAA
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 44219
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;liber8.cityinthe.cloud.                IN      AAAA

;; ANSWER SECTION:
liber8.cityinthe.cloud. 3600    IN      AAAA    2ecd:b3d:2f0c:e72b:da9:f4ee:81e:d62d

;; Query time: 0 msec
;; SERVER: 10.7.71.132#53(10.7.71.132)
;; WHEN: Sun Apr 13 01:03:51 UTC 2025
;; MSG SIZE  rcvd: 79
```

`2ecd:b3d:2f0c:e72b:da9:f4ee:81e:d62d`

Q3 - 15 points  
What is the flag txt record for `flag.liber8.cityinthe.cloud`?

```
┌──(root㉿kali)-[~]
└─# dig flag.liber8.cityinthe.cloud @resolver TXT

; <<>> DiG 9.16.11-Debian <<>> flag.liber8.cityinthe.cloud @resolver TXT
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 49619
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;flag.liber8.cityinthe.cloud.   IN      TXT

;; ANSWER SECTION:
flag.liber8.cityinthe.cloud. 3600 IN    TXT     "SKY-XJPO-5751"

;; Query time: 0 msec
;; SERVER: 10.7.71.132#53(10.7.71.132)
;; WHEN: Sun Apr 13 01:11:32 UTC 2025
;; MSG SIZE  rcvd: 82
```

`SKY-XJPO-5751`

Q4 - 15 points  
What is the domain that `redirect.liber8.cityinthe.cloud` redirects to?

```
┌──(root㉿kali)-[~]
└─# dig redirect.liber8.cityinthe.cloud @resolver

; <<>> DiG 9.16.11-Debian <<>> redirect.liber8.cityinthe.cloud @resolver
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 12440
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;redirect.liber8.cityinthe.cloud. IN    A

;; ANSWER SECTION:
redirect.liber8.cityinthe.cloud. 600 IN CNAME   r3d1r3ct3d.liber8.cityinthe.cloud.

;; Query time: 1 msec
;; SERVER: 10.7.71.132#53(10.7.71.132)
;; WHEN: Sun Apr 13 01:12:17 UTC 2025
;; MSG SIZE  rcvd: 85
```

`r3d1r3ct3d.liber8.cityinthe.cloud`

Q5 - 15 points  
What is the TTL for the redirect on `redirect.liber8.cityinthe.cloud`? (In seconds)

- Refer to the code that was queried above

`redirect.liber8.cityinthe.cloud. 600 IN CNAME   r3d1r3ct3d.liber8.cityinthe.cloud.`

`600`

Q6 - 15 points  
What is the IPv4 address for the domain that `redirect.liber8.cityinthe.cloud` redirects to?

- Query the IPv4 Address for the redirected domain

```
┌──(root㉿kali)-[~]
└─# dig r3d1r3ct3d.liber8.cityinthe.cloud @resolver A

; <<>> DiG 9.16.11-Debian <<>> r3d1r3ct3d.liber8.cityinthe.cloud @resolver A
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 54799
;; flags: qr aa rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 1232
;; QUESTION SECTION:
;r3d1r3ct3d.liber8.cityinthe.cloud. IN  A

;; ANSWER SECTION:
r3d1r3ct3d.liber8.cityinthe.cloud. 3600 IN A    39.199.63.8

;; Query time: 1 msec
;; SERVER: 10.7.71.132#53(10.7.71.132)
;; WHEN: Sun Apr 13 01:14:13 UTC 2025
;; MSG SIZE  rcvd: 78
```

`39.199.63.8`

Q7 - 15 points  
What is the domain of the mail exchange server that handles the majority of the email for `mail.liber8.cityinthe.cloud`?

