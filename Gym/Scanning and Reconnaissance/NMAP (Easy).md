Test your understanding of port scanning by scanning ports.cityinthe.cloud and answering these questions.

Note: You are allowed to run automated tools on this target.


Ran a nmap scan:

```
root@DESKTOP:~# nmap ports.cityinthe.cloud
Starting Nmap 7.95 ( https://nmap.org ) at 2025-03-30 20:42 PDT
Nmap scan report for ports.cityinthe.cloud (34.199.237.244)
Host is up (0.090s latency).
rDNS record for 34.199.237.244: ec2-34-199-237-244.compute-1.amazonaws.com
Not shown: 996 filtered tcp ports (no-response)
PORT      STATE SERVICE
7/tcp     open  echo
13/tcp    open  daytime
37/tcp    open  time
16080/tcp open  osxwebadmin

Nmap done: 1 IP address (1 host up) scanned in 17.80 seconds

```


Q1 - 15 points

What is the lowest open TCP port on the system?

`7`

Q2 - 15 points

What is the second lowest open TCP port on the system?

`13`

Q3 - 15 points

What is the third lowest open TCP port on the system?

`37`

Q4 - 20 points

What is the lowest open UDP port on the system?

- Perform a 

Q5 - 20 points

What software is being run on TCP port 16080?