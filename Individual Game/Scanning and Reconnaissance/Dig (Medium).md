
We've gained access to an internal DNS resolver that liber8tion has been using for their servers. Conduct a scan of the DNS records for liber8.cityinthe.cloud.

MAKE SURE TO USE THE DEVICE WITH THE resolver HOSTNAME IN THE PROVIDED TERMINAL AS YOUR DNS RESOLVER

- Use [`dig`](https://www.ibm.com/docs/pl/aix/7.1?topic=d-dig-command) command

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



Q3 - 15 points  
What is the flag txt record for `flag.liber8.cityinthe.cloud`?


Q4 - 15 points  
What is the domain that `redirect.liber8.cityinthe.cloud` redirects to?


Q5 - 15 points  
What is the TTL for the redirect on `redirect.liber8.cityinthe.cloud`? (In seconds)

 
Q6 - 15 points  
What is the IPv4 address for the domain that `redirect.liber8.cityinthe.cloud` redirects to?


Q7 - 15 points  
What is the domain of the mail exchange server that handles the majority of the email for `mail.liber8.cityinthe.cloud`?