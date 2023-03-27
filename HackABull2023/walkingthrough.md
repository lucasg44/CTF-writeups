# Walking through

### Overview
Walking through was an 50 point general skills challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 1:28 PM.

### The problem
I've accidentally dropped my flag into this image and its being stubborn about getting out. Could you help?

Download the file [here](https://ctf.hackabull.dev/files/cc2664a5dbbf2eb4f4afc869a3f0ae09/wcscLogo.png?token=eyJ1c2VyX2lkIjoxNCwidGVhbV9pZCI6NSwiZmlsZV9pZCI6MTJ9.ZCG1RA.5dOuM6BbNCL_niJZL-8-tIQSstk)

### The solution
At the beginning, I realized this was a png file, so I used a binwalk command
``````bash
binwalk -e wcscLogo.png
``````

After using the binwalk command, I pulled an extracted file, which led me to a zip file in the extracted directory. The zip file contained a "flag.txt" file that was password protected.
In order to find the password for the flag file, I ran strings on the wcscLogo and came across this:
``````text
b2RkbG9va2luZ3Bhc3N3b3JkMTIz
``````

This string was the password for the flag.txt file, and that txt file gave me the flag

### TL;DR
After running binwalk on the png, I got a zip file in the extracted directory. I found the password in the strings of the picture, and used the password to pull the flag.

### Flag
WCSC_HackaBull{UKnowHow2BinWalkLOL}


