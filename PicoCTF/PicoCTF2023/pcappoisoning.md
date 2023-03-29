# Pcap Poisoning

### Overview
This challenge is a forensics challenge from PicoCTF 2023, I completed this challenge on my own.

### The problem
How about some hide and seek heh? Download [this file](https://artifacts.picoctf.net/c/400/trace.pcap) and find the flag.
(No hints)

### The solution
Getting started, I ran a strings command on the file.
``````bash
strings trace.pcap 
``````

After looking around, I noticed a lot of pointless clutter, so I tried to see if the file outright stated the flag with this command:
``````bash
strings trace.pcap | grep pico
``````

My guess was right, the file outright stated the flag and it was pulled with this command.

### TL;DR
I used a strings command with a grep pipe to immediately pull the flag.

### Flag
picoCTF{P64P_4N4L7S1S_SU55355FUL_ba1a6097}
