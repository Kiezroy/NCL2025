
This file appears to be changed in some way. Can you recover the original?

(You can use either CyberChef or a tool of your choosing to complete this challenge)


What is the original file type? (25 pts)

- At first, the file seems to be JPG/JEPG but is not
- There is a JPEG format error

```
┌──(kali㉿kali)-[~/Downloads]
└─$ exiftool flag.jpeg 
ExifTool Version Number         : 13.00
File Name                       : flag.jpeg
Directory                       : .
File Size                       : 7.1 kB
File Modification Date/Time     : 2025:04:09 22:00:41-04:00
File Access Date/Time           : 2025:04:09 22:00:43-04:00
File Inode Change Date/Time     : 2025:04:09 22:00:41-04:00
File Permissions                : -rw-rw-r--
File Type                       : JPEG
File Type Extension             : jpg
MIME Type                       : image/jpeg
Warning                         : JPEG format error

```

- Run strings on the file 
- Discover important words like "JFIF", "IHDR", "IDAT", etc...
- Discover IHDR and IDAT is PNG format

![](attachments/Pasted%20image%2020250409192230.png)

`PNG`

What is the flag? (75 pts)

- Use `hexedit` tool to view the hex format and look at the [magic bytes](https://en.wikipedia.org/wiki/List_of_file_signatures)
- Fix the magic bytes to match PNG

![](attachments/Pasted%20image%2020250409192731.png)

- Since JPG was 12 bytes, fill the extra 4 bytes with bytes from any PNG image

![](attachments/Pasted%20image%2020250409192835.png)

- Open the flag.jpeg file now and discover the flag

![](attachments/Pasted%20image%2020250409193037.png)


`SKY-DSFG-5792`