
We have identified what we believe to be one of Liber8tion's servers. We need you to conduct a TCP scan on the server.

The hostname of the server is `target`

- Run a `nmap` scan

```
┌──(root㉿attacker)-[~]
└─# nmap -p- -sC -sV target

PORT     STATE SERVICE         VERSION
17/tcp   open  qotd?
79/tcp   open  finger?
|_finger: ERROR: Script execution failed (use -d to debug)
80/tcp   open  http            SimpleHTTPServer 0.6 (Python 3.11.2)
|_http-server-header: SimpleHTTP/0.6 Python/3.11.2
|_http-title: Directory listing for /
1337/tcp open  waste?
4000/tcp open  remoteanything?
MAC Address: 02:42:0A:06:92:E4 (Unknown)
```

Q1 - 25 points  
What is the lowest port on the `target` machine?




Q2 - 25 points  
What is the highest port on the `target` machine?




Q3 - 25 points  
What is the version of the service running on port 80?

``

`0.6`

Q4 - 25 points  
What is the flag found on one of the hosted services on target?