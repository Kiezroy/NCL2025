Our analysts have obtained password dumps storing hacker passwords. After obtaining a few plaintext passwords, it appears that they are based on Pokemon.

- Create `hashes.txt` file with all the hashes
- Find a wordlist online of a pokemon wordlist
- Apply a ruleset to hashcat to make the brute forcing more diverse

```
┌──(kali㉿kali)-[~]
└─$ hashcat -m 0 hashes.txt ./Downloads/pokemon-list-en.txt -r /usr/share/hashcat/rules/best64.rule 
hashcat (v6.2.6) starting

OpenCL API (OpenCL 3.0 PoCL 6.0+debian  Linux, None+Asserts, RELOC, LLVM 17.0.6, SLEEF, DISTRO, POCL_DEBUG) - Platform #1 [The pocl project]
============================================================================================================================================
* Device #1: cpu-sandybridge-AMD Ryzen 5 5600X 6-Core Processor, 2643/5351 MB (1024 MB allocatable), 4MCU

Minimum password length supported by kernel: 0
Maximum password length supported by kernel: 256

Hashes: 5 digests; 5 unique digests, 1 unique salts
Bitmaps: 16 bits, 65536 entries, 0x0000ffff mask, 262144 bytes, 5/13 rotates
Rules: 77

Optimizers applied:
* Zero-Byte
* Early-Skip
* Not-Salted
* Not-Iterated
* Single-Salt
* Raw-Hash

ATTENTION! Pure (unoptimized) backend kernels selected.
Pure kernels can crack longer passwords, but drastically reduce performance.
If you want to switch to optimized kernels, append -O to your commandline.
See the above message to find out about the exact limits.

Watchdog: Temperature abort trigger set to 90c

Host memory required for this attack: 1 MB

Dictionary cache built:
* Filename..: ./Downloads/pokemon-list-en.txt
* Passwords.: 721
* Bytes.....: 6063
* Keyspace..: 55517
* Runtime...: 0 secs

The wordlist or mask that you are using is too small.
This means that hashcat cannot use the full parallel power of your device(s).
Unless you supply more work, your cracking speed will drop.
For tips on supplying more work, see: https://hashcat.net/faq/morework

Approaching final keyspace - workload adjusted.           

54c10b9736b70e75c6e505f340b6e2f1:basculin                 
83b020b0a7b3c353e1c11b1647b53cda:celebi                   
999cae1e22fe69d89d6f56e3050f18cb:goldeen                  
a532443f3e04a9e00295a8cd2a75e080:golduck                  
b8a24794813a47521b4be55747e0665a:rotom                    
                                                          
Session..........: hashcat
Status...........: Cracked
Hash.Mode........: 0 (MD5)
Hash.Target......: hashes.txt
Time.Started.....: Tue Apr  8 22:34:00 2025 (0 secs)
Time.Estimated...: Tue Apr  8 22:34:00 2025 (0 secs)
Kernel.Feature...: Pure Kernel
Guess.Base.......: File (./Downloads/pokemon-list-en.txt)
Guess.Mod........: Rules (/usr/share/hashcat/rules/best64.rule)
Guess.Queue......: 1/1 (100.00%)
Speed.#1.........: 17226.7 kH/s (2.24ms) @ Accel:512 Loops:77 Thr:1 Vec:8
Recovered........: 5/5 (100.00%) Digests (total), 5/5 (100.00%) Digests (new)
Progress.........: 55517/55517 (100.00%)
Rejected.........: 0/55517 (0.00%)
Restore.Point....: 0/721 (0.00%)
Restore.Sub.#1...: Salt:0 Amplifier:0-77 Iteration:0-77
Candidate.Engine.: Device Generator
Candidates.#1....: abomasnow -> zdezde
Hardware.Mon.#1..: Util: 26%

Started: Tue Apr  8 22:33:58 2025
Stopped: Tue Apr  8 22:34:01 2025

```


| User                                                                                                 | Password Ciphertext              | Answer     |
| ---------------------------------------------------------------------------------------------------- | -------------------------------- | ---------- |
| ![](https://assets.cyberskyline.com/img/avatars/small/elliot.jpg?t=3)<br><br>Elliot<br><br>20 points | a532443f3e04a9e00295a8cd2a75e080 | `golduck`  |
| ![](https://assets.cyberskyline.com/img/avatars/small/justen.jpg?t=3)<br><br>Justen<br><br>20 points | 54c10b9736b70e75c6e505f340b6e2f1 | `basculin` |
| ![](https://assets.cyberskyline.com/img/avatars/small/lena.png?t=3)<br><br>Lena<br><br>20 points     | b8a24794813a47521b4be55747e0665a | `rotom`    |
| ![](https://assets.cyberskyline.com/img/avatars/small/chris.jpg?t=3)<br><br>Chris<br><br>20 points   | 83b020b0a7b3c353e1c11b1647b53cda | `celebi`   |
| ![](https://assets.cyberskyline.com/img/avatars/small/ade.jpg?t=3)<br><br>Ade<br><br>20 points       | 999cae1e22fe69d89d6f56e3050f18cb | `goldeen`  |
