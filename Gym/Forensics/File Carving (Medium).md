
The security team has found a rather strange file exiting the network, we're not sure if it's containing any sensitive information. Help us identify what's in it.

[green_file](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015b9ad4ea5fef1fce971/65b015baad4ea5fef1fce9dd/65b015baad4ea5fef1fce9df/download?t=3)


Q1 - 10 points

This file initially looks like something green, what's the file format of this green file?

- Use exiftool

```
┌──(kali㉿kali)-[~/Downloads]
└─$ exiftool green_file 
ExifTool Version Number         : 13.00
File Name                       : green_file
Directory                       : .
File Size                       : 4.5 kB
File Modification Date/Time     : 2025:04:09 18:56:01-04:00
File Access Date/Time           : 2025:04:09 18:56:01-04:00
File Inode Change Date/Time     : 2025:04:09 18:56:01-04:00
File Permissions                : -rw-rw-r--
File Type                       : PNG
File Type Extension             : png
MIME Type                       : image/png
Image Width                     : 63
Image Height                    : 36
Bit Depth                       : 8
Color Type                      : RGB with Alpha
Compression                     : Deflate/Inflate
Filter                          : Adaptive
Interlace                       : Noninterlaced
Significant Bits                : 8 8 8 8
Warning                         : [minor] Trailer data after PNG IEND chunk
Image Size                      : 63x36
Megapixels                      : 0.002

```

`PNG`

Q2 - 25 points

How many files can be extracted from the binary blob?

- Use [binwalk](https://github.com/ReFirmLabs/binwalk)

```
┌──(kali㉿kali)-[~/Downloads]
└─$ binwalk green_file 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
0             0x0             PNG image, 63 x 36, 8-bit/color RGBA, non-interlaced
3243          0xCAB           gzip compressed data, from Unix, last modified: 2017-02-14 05:32:27
3605          0xE15           PNG image, 24 x 24, 8-bit/color RGBA, non-interlaced
3818          0xEEA           PNG image, 24 x 24, 8-bit/color RGBA, non-interlaced
4040          0xFC8           PNG image, 24 x 24, 8-bit/color RGBA, non-interlaced
4264          0x10A8          PNG image, 24 x 24, 8-bit/color RGBA, non-interlaced
```

`6`

Q3 - 50 points

What is the hidden flag in the file?

