
Our analysts have gone a little meme-crazy, no cap. Find the flags and don't get cooked.

[ForYou.jpg](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860df0/67d81dc67c06227c4a515406/67d821de7c06227c4a515a0a/67f53cd9114edb472ac0413d/download?t=3)

![](../../attachments/Pasted%20image%2020250412090052.jpg)

- Use `binwalk` to extract embedded / hidden files

```
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk -e ForYou.jpg 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
663360        0xA1F40         Zip archive data, at least v2.0 to extract, compressed size: 134300, uncompressed size: 134590, name: 1Scroll.jpg
797701        0xC2C05         Zip archive data, at least v2.0 to extract, compressed size: 1008, uncompressed size: 2620, name: 2NeverGoingToGIve.txt
798760        0xC3028         Zip archive data, at least v2.0 to extract, compressed size: 86086, uncompressed size: 86133, name: 3Sky.jpg
884884        0xD8094         Zip archive data, at least v2.0 to extract, compressed size: 126, uncompressed size: 1032, name: 4Congrats.txt
885053        0xD813D         Zip archive data, at least v2.0 to extract, compressed size: 121095, uncompressed size: 121625, name: 5Wise.jpg
1006187       0xF5A6B         Zip archive data, at least v2.0 to extract, compressed size: 91, uncompressed size: 1181, name: 6Bussin.txt
1006319       0xF5AEF         Zip archive data, at least v2.0 to extract, compressed size: 74475, uncompressed size: 76235, name: 7Buzz.jpg
1080833       0x107E01        Zip archive data, at least v2.0 to extract, compressed size: 765, uncompressed size: 1212, name: 8More.txt

WARNING: One or more files failed to extract: either no utility was found or it's unimplemented

```

Q1 - 35 points  
What is the flag found on an image?



Q2 - 35 points  
What is the secret flag that one image hints about?



Q3 - 35 points  
What is the super secret flag encoded in base64?