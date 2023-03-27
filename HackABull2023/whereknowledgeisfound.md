# Where knowledge is found

### Overview
Where knowledge is found was an 175 point reverse engineering challenge at Hack-a-bull 2023. This challenge was solved on March 26th at 12:44 PM. This challenge was created by Jack W.

### The problem
We've managed to intercept a binary file from the network of one of our adversaries. We believe that the file contains important information, but we haven't been able to find much of anything (aside from poor spelling). Maybe you can take a look at it?

Download the file [here](https://ctf.hackabull.dev/files/8b54ab5d3338eca31554de55309dd500/knowledge?token=eyJ1c2VyX2lkIjoxNCwidGVhbV9pZCI6NSwiZmlsZV9pZCI6MTh9.ZCHR3g.xLrFb2s5D3Ow4r7e710XpsL5k0c)

### The solution
After downloading the ELF file, I decided to run the strings command on it, which gave me nothing useful.

After trying the string command, I went to an ltrace command on the file and recived the following
``````bash
ltrace ./knowledge test
strcmp("WCSC_HackaBull23{Sn00p3d_L1br4ry"..., "test") = -29
puts("Incorrect. Snoop no further."Incorrect. Snoop no further.
)           = 29
+++ exited (status 0) +++
``````

Knowing it printed half of the string, I switched things up to include "-s 64" to be able to read the full string and flag
``````bash
ltrace -s 64 ./knowledge test
strcmp("WCSC_HackaBull23{Sn00p3d_L1br4ry-St0l3n_S3cr3t5}", "test") = -29
puts("Incorrect. Snoop no further."Incorrect. Snoop no further.
)           = 29
+++ exited (status 0) +++
``````

### TL;DR
Using ltrace on the ELF file gave me the string.

### Flag
WCSC_HackaBull23{Sn00p3d_L1br4ry-St0l3n_S3cr3t5}

