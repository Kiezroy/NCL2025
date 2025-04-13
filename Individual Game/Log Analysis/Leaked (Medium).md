
Our analysts recovered data that was taken from a social media SQL database and was leaked via the Liber8tion group on the dark web.

[social_data.sql](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860df0/67d81d637c06227c4a515380/67d8222e7c06227c4a515ac6/67f420d0114edb472abc321b/download?t=3)

Q1 - 10 points  
How many users were compromised in this breach?

- Just look at how many lines there are and go to end of file

`982`

Q2 - 20 points  
What is the date and time (in UTC) of the first account to join the social media site? Round to the nearest minute.

- This is the first account

`insert into Hacked_data (email, phone, followers_count, following_count, join_date, is_verified, post_likes_avg, post_comments_avg) values ('vpepper0@cityinthe.cloud', '856-161-9145', 799, 204, '1742814687000', true, 588, 23);`

- The `join_date` value is `1742814687000` which is a timestamp in the Epoch Unix format
- Use a [converter](https://www.epochconverter.com/) to covert to human readable time

![](../../attachments/Pasted%20image%2020250413115735.png)

`Monday, March 24, 2025 4:11:27 AM`

Q3 - 20 points  
What is the email for the account with the most followers?




Q4 - 20 points  
How many of the listed users are verified?