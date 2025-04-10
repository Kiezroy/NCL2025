
[code.png](https://cyberskyline.com/artifact/65e54bcb52369daf3dc4725b/677847d9b4401661d5860ded/67e5b9e7660b44323954acd8/6058d4538e96845bcd2ff665/6058d4ad8e96845bcd2ff666/download?t=3)

![](Pasted%20image%2020250403170208.png)

We have uncovered a picture that contains a flag, but it seems to be missing some data. Can you recover the missing flag?

What version of QR Code is present in the image? (10 pts)

![](Pasted%20image%2020250403172321.png)

- Count the amount of modules on each side

`Version 2`


What is the error correction level? (10 pts)

"QR codes come with four levels of error correction – Low (L) – 7%, Medium (M)- 15%, Quartile (Q) – 25%, and High (H) – 30%. Each level provides a greater degree of resilience at the cost of reducing the storage capacity of the QR code." 

Source: https://tritonstore.com.au/common-qr-code-mistakes/

Source: https://scanova.io/blog/qr-code-error-correction/
![](error-correction-level-1024x512.webp)

`Level H`


What is the number for the mask pattern? (10 pts)

![](Pasted%20image%2020250403180303.png)![](Pasted%20image%2020250403180310.png)

`3`


What is the flag? (40 pts)

- Use https://merri.cx/qrazybox/ to reconstruct the QR code
- Fill in each of the modules (the black and white squares)
- Ensure to specify QR Code version as 25x25, Module size of 10px, and EC Level as H, Mask Pattern as 3
![](Pasted%20image%2020250403183934.png)

![](Pasted%20image%2020250403183925.png)

- Most most of the QR code is reconstructed, view it with Tools > Extract QR information
![](Pasted%20image%2020250403184241.png)

![](Pasted%20image%2020250403184018.png)

![](Pasted%20image%2020250403184025.png)

![](Pasted%20image%2020250403184034.png)

`SKY-QRCD-7492`