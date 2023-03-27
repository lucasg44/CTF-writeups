# Eavesdropping

### Overview
Eavesdropping was an 100 point forensics challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 1:42 PM. This challenge was created by Dewey.

### Resources
https://www.dcode.fr/caesar-cipher

This website provided my team with a way to get the brute force aspect down for cesar cypher

### The problem
Our IDS picked up some uncategorized traffic, can you figure out what happened?
Download the file [here](https://ctf.hackabull.dev/files/ed881c4758ece43fe62a191bd6c5a51a/eavesdropping.pcapng?token=eyJ1c2VyX2lkIjoxNCwidGVhbV9pZCI6NSwiZmlsZV9pZCI6Mn0.ZCEHyw.iD1sE8sk4_WPAWjtWHJulaRNxqs)

### The solution
This problem lead us to a massive wireshark file, in order to pull an output I used the command to pull relevant strings from the pcapng file
``````bash
strings eavesdropping.pcapng
``````

Pulling this command led to one noteable output
``````text
JPFP_UnpxnOhyy23{s10j!at_j1gu_gu3_fge34zf00}
``````

Using this output, we plugged it into as many cyphers that my team could imaging until we stumbled onto a cesar cypher. After running the text through our resource, we stumbled upon the flag through a cesar cypher with a rotation of 13.

### TL;DR
We found a string in the pcapng file that looked similar to a flag format, so we ran a cesar cypher to get the decoded flag.

### Flag
WCSC_HackaBull23{f10w!ng_w1th_th3_str34ms00}
