# FindAndOpen

### Overview
This challenge was a forensics challenge on PicoCTF 2023. I completed this challenge on my own.

### Resources
https://www.base64decode.org/

This helped me decode the base64 code

### The problem
Someone might have hidden the password in the trace file. 
Find the key to unlock this [file](https://artifacts.picoctf.net/c/495/flag.zip). This [tracefile](https://artifacts.picoctf.net/c/495/dump.pcap) might be good to analyze.

(Hint 1) Download the pcap and look for the password or flag.

(Hint 2) Don't try to use a password cracking tool, there are easier ways here.

### The solution
I started by looking at the file with a strings command, which gave me 3 unique outputs
``````text
iBwaWNvQ1RGe1Could the flag have been splitted?
AABBHHPJGTFRLKVGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8=
PBwaWUvQ1RGe1Maybe try checking the other file?
``````

I started by plugging the following into base64 decode:
``````text
iBwaWNvQ1RGe1PBwaWUvQ1RGe1
AABBHHPJGTFRLKVGhpcyBpcyB0aGUgc2VjcmV0OiBwaWNvQ1RGe1IzNERJTkdfTE9LZF8=
``````
Which gave me:
``````text
Xpie/CTF{P�<This is the secret: picoCTF{R34DING_LOKd_
``````

I used the half flag provided after the "This is the secret" line as the password and it gave me the flag

### TL;DR
The file provided a half flag, which was actually the password to unlock access to the full flag.

### Flag
picoCTF{R34DING_LOKd_fil56_succ3ss_0f2afb1a}
