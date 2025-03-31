Analyze a custom application login event log to help us understand user behavior.

[login.log](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015dbad4ea5fef1fceaa6/65b02e02ad4ea5fef1fd1ea1/65b02e02ad4ea5fef1fd1ea3/download?t=3)

Q1 - 5 points

How many total login attempts were made in this log?

- Look at how many lines were made

![](attachments/Pasted%20image%2020250330173725.png)

`6063`

Q2 - 15 points

How many unique usernames appear in this log?

`cat login.log | cut -f 3 | sort | uniq | wc -l`

`1879`

Q3 - 20 points

What is the username with the most login attempts?

`awk '{print $4}' login.log  | sort | uniq -c | sort -nr`

`ntory`

Q4 - 20 points

How many attempts were made for the username with the most login attempts?

`cat login.log | grep ntory | wc -l`

`124`

Q5 - 20 points

What is the date with the most login attempts?

`cat login.log | cut -d " " -f 1 | sort | uniq -c | sort -n`

``` 
	94 2011-03-04
    116 2011-03-06
    122 2011-03-27
    130 2011-03-05
    142 2011-03-20
    143 2011-03-13
    146 2011-03-26
    151 2011-03-12
    163 2011-03-19
    207 2011-03-07
    220 2011-03-31
    229 2011-03-25
    230 2011-03-11
    236 2011-03-18
    241 2011-03-24
    243 2011-03-30
    245 2011-03-08
    245 2011-03-29
    255 2011-03-21
    263 2011-03-09
    263 2011-03-17
    263 2011-03-22
    264 2011-03-16
    268 2011-03-15
    283 2011-03-10
    292 2011-03-28
    299 2011-03-14
    310 2011-03-23
```

`2011-03-23`

Q6 - 20 points

What is the username that had logins from the most unique IP addresses?