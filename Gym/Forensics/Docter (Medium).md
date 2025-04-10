
We think this document is hiding something. Can you find what is hidden?

[SuperAwesomeDoc.docx](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860dea/65b015b9ad4ea5fef1fce971/65b02e0bad4ea5fef1fd2115/65b02e0bad4ea5fef1fd2117/download?t=3)

Q1 - 20 points

What is the name of the hidden file containing the flag?

- `.docx` is actually ZIP compressed archive
- Can unzip if change to a zip file

```
┌──(kali㉿kali)-[~/Downloads]
└─$ mv SuperAwesomeDoc.docx SuperAwesomeDoc.zip                                                   
┌──(kali㉿kali)-[~/Downloads]
└─$ unzip SuperAwesomeDoc.zip 
Archive:  SuperAwesomeDoc.zip
  inflating: [Content_Types].xml     
   creating: _rels/
  inflating: _rels/.rels             
   creating: word/
  inflating: word/settings.xml       
  inflating: word/document.xml       
   creating: word/theme/
  inflating: word/theme/theme1.xml   
  inflating: word/styles.xml         
   creating: word/media/
  inflating: word/media/image4.png   
  inflating: word/media/image2.png   
  inflating: word/media/image0.png   
  inflating: word/media/image1.png   
  inflating: word/media/image3.png   
  inflating: word/fontTable.xml      
   creating: word/_rels/
  inflating: word/_rels/document.xml.rels  
  inflating: word/numbering.xml      

```

- Explore the contents and find the media folder with the flag

![](Pasted%20image%2020250409194355.png)

`image0.png`

Q2 - 80 points

What is the flag?

![](Pasted%20image%2020250409194422.png)

`SKY-RATL-8439`