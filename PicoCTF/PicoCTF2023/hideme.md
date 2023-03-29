# HideMe

### Overview
This challenge is a forensics challenge from PicoCTF 2023, I completed this challenge on my own.

### Resources
https://infosecwriteups.com/beginners-ctf-guide-finding-hidden-data-in-images-e3be9e34ae0d

This resouce helped me learn about binwalk

### The problem
Every file gets a flag. 
The SOC analyst saw one image been sent back and forth between two people. They decided to investigate and found out that there was more than what meets the eye [here](https://artifacts.picoctf.net/c/489/flag.png).
(No hints)

### The solution
In ordet to get started, I ran a strings command on the png file, which gave me nothing.

After some research, I ran the binwalk command on the file.
``````bash
binwalk -e flag.png
``````

This command pulled a secret file, which contained an image that had the flag

### TL;DR
I used binwalk to pull a secret image that had the flag

### Flag
picoCTF{Hiddinng_An_imag3_within_@n_ima9e_c31884c7}
