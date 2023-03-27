# Yar har! I am a pirate!

### Overview
I am a pirate was an 200 point forensics challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 2:30 PM. This challenge was created by Jacob H.

### Resources
https://gchq.github.io/CyberChef/

Cyberchef helped me decode the hexidecimal in this problem.

### The problem
The cool kids use peer-to-peer networking these days.

Download the file [here](https://ctf.hackabull.dev/files/4c2039865659909d5d7d4ae8baeff3ea/chall.torrent?token=eyJ1c2VyX2lkIjoxNCwidGVhbV9pZCI6NSwiZmlsZV9pZCI6N30.ZCGzVg.qYD7k_UI8kL5tcQkT_DY6-1bVno)

### The solution
After starting on the challenge, I used a string command to pull the noteable information from the flag

``````bash
strings chall.torrent
``````

After using this command, I noticed that there were lots of hyperlinks, but one line did stand out from the crowd

``````text
comment40:574353435f4861636b6142756c6c32337b6d795f10
``````

This text stood out because once I decoded the comment from hexidecimal, I noticed it provided the first half of the flag. I continued to pull chunks from the file and decoded them in hexidecimal to get the full flag

### TL;DR
After opening the torrent file, I decoded certain number combinations from hex to get small portions of the flag, then I combined them to get the full flag.

### Flag
WCSC_HackaBull23{my_tr4ck3r_br0k3_h3lp_m3}
