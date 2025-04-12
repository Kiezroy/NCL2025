
There's a reason almost all websites these days use HTTPS.

[access.log](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860df0/67d81d637c06227c4a515380/67d8221b7c06227c4a515a8f/67f3cdf638234dd15b2c5395/download?t=3)

Q1 - 10 points  
What is the domain of the third HTTP request in the log?

- Filter the log for only real HTTP requests
- The "CONNECT" are not requests but are actually tunnel setups for HTTPS

```
┌──(kali㉿kali)-[~/Downloads]
└─$ grep -E " (GET|POST|HEAD|PUT|DELETE|OPTIONS|PATCH) " access.log

1743959510.401    138 ::1 TCP_MISS/200 1582 GET http://example.com/ - HIER_DIRECT/96.7.128.198 text/html
1743959659.186    168 127.0.0.1 TCP_MISS/200 790 POST http://o.pki.goog/wr2 - HIER_DIRECT/172.217.0.67 application/ocsp-response
1743959680.158      0 127.0.0.1 TCP_MISS_ABORTED/000 0 GET http://httpforever.com/js/init.min.js - HIER_NONE/- -
1743959680.192      0 127.0.0.1 TCP_MISS_ABORTED/000 0 GET http://httpforever.com/css/style.min.css - HIER_NONE/- -
1743959687.348    165 127.0.0.1 TCP_MISS/200 941 POST http://status.rapidssl.com/ - HIER_DIRECT/23.55.219.177 application/ocsp-response
1743959687.484    194 127.0.0.1 TCP_MISS/200 941 POST http://ocsp.digicert.com/ - HIER_DIRECT/23.55.219.177 application/ocsp-response
1743959688.642    194 127.0.0.1 TCP_MISS/200 2054 POST http://ocsp.globalsign.com/gsrsaovsslca2018 - HIER_DIRECT/151.101.130.133 application/ocsp-response
1743959688.743    184 127.0.0.1 TCP_MISS/200 1132 POST http://ocsp.r2m02.amazontrust.com/ - HIER_DIRECT/108.156.203.96 application/ocsp-response
1743959690.324    133 127.0.0.1 TCP_MISS/200 1081 POST http://ocsp.sectigo.com/ - HIER_DIRECT/104.18.38.233 application/ocsp-response
1743959690.536    123 127.0.0.1 TCP_MISS/200 941 POST http://ocsp.digicert.com/ - HIER_DIRECT/23.55.219.177 application/ocsp-response
1743959691.087    144 127.0.0.1 TCP_MISS/200 1132 POST http://ocsp.r2m02.amazontrust.com/ - HIER_DIRECT/108.156.203.96 application/ocsp-response

```

`http://httpforever.com/js/init.min.js`

Q2 - 15 points  
At what timestamp did the server respond to the HTTP request for the site in Q1? (Use the same format from the log)

Here is the format of the logs:

`<timestamp> <duration> <client IP> <cache result>/<HTTP code> <bytes> <method> <URL> <RFC931> <hierarchy code>/<server IP> <MIME type>`

`1743959680.158`

Q3 - 15 points  
What is the IP address of the server hosting `www.delta.com` in the first CONNECT request?

- Filter for www.delta.com logs
- Look at the first log

```
┌──(kali㉿kali)-[~/Downloads]
└─$ cat access.log | grep "www.delta.com" | head -n 1
1743959685.292     93 127.0.0.1 TCP_TUNNEL/200 39 CONNECT www.delta.com:443 - HIER_DIRECT/96.16.70.40 -
```

`96.16.70.40`

Q4 - 15 points  
How many NONE_NONE/000 errors are present in the log?



Q5 - 15 points  
How many successful connections were made to push.services.mozilla.com?




Q6 - 15 points  
How many total POST requests were made?



Q7 - 15 points  
What is the third most frequently accessed domain path in the log?