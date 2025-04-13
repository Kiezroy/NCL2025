
Our analysts recovered data that was taken from a social media SQL database and was leaked via the Liber8tion group on the dark web.

[social_data.sql](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860df0/67d81d637c06227c4a515380/67d8222e7c06227c4a515ac6/67f420d0114edb472abc321b/download?t=3)

Q1 - 10 points  
How many users were compromised in this breach?

- Just look at how many lines there are and go to end of file

`982`

Q2 - 20 points  
What is the date and time (in UTC) of the first account to join the social media site? Round to the nearest minute.

- Create a database with the table `Hacked_data` using `sqlite` GUI
- Replicate the same fields 

```
CREATE TABLE "Hacked_data" (
	"email"	TEXT,
	"phone"	TEXT,
	"followers_count"	INTEGER,
	"following_count"	INTEGER,
	"join_date"	INTEGER,
	"is_verified"	INTEGER,
	"post_likes_avg"	INTEGER,
	"post_comments_avg"	INTEGER
)
```

- Execute all the SQL data from the logs > Sort by the oldest date

![](../../attachments/Pasted%20image%2020250413121531.png)

![](../../attachments/Pasted%20image%2020250413121556.png)

- The `join_date` value is `1742601698000` which is a timestamp in the Epoch Unix format
- Use a [converter](https://www.epochconverter.com/) to covert to human readable time

![](../../attachments/Pasted%20image%2020250413121614.png)

`Saturday, March 22, 2025 12:01:38 AM`

Q3 - 20 points  
What is the email for the account with the most followers?

- Sort by `followers_count`


Q4 - 20 points  
How many of the listed users are verified?