
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



Q5 - 10 points

What version of the Googlebot visited the website?

Q6 - 10 points

Which IP address attempted to exploit the shellshock vulnerability?

Q7 - 10 points

What was the most popular version of Firefox used for browsing the website?

Q8 - 10 points

What is the most common HTTP method used?

Q9 - 10 points

What is the second most common HTTP method used?

Q10 - 10 points

How many requests were for \x04\x01\x00P\xC6\xCE\x0Eu0\x00?