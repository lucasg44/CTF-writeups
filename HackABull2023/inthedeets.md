# In the deets...

### Overview
In the deets was an 100 point forensics challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 1:39 PM. This challenge was created by Dewey.

### The problem
Download the file [here](https://ctf.hackabull.dev/files/51908292ea3572e5c42b0cce813536ea/in_the_deets.pcapng?token=eyJ1c2VyX2lkIjoxNCwidGVhbV9pZCI6NSwiZmlsZV9pZCI6M30.ZCGx2Q.VZ59bthzdmrVHd0o949cRAfl-tQ)

### The solution
I started off by simply running a strings command on the pcapng file
``````bash
strings in_the_deets.pcapng
``````

After a little bit of searching, the flag was clearly visible

### TL;DR
Running the strings command exposed the flag clearly

### Flag
WCSC_HackaBull23{ez_en0ugh}
