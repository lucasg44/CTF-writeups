# Git commit

### Overview
This challenge was a OSINT challenge as a part of CyberHack 2023, I solved this challenge completely on my own. This challenge was rated an easy challenge on Hackthebox.

### The Problem
Are you really committed to becoming an OSINT master? Because version-control and collaboration platforms may expose valuable information and Jonathan is using one of them.

### The Solution
Looking at the instructions, version-control and collaboration platforms are important here. So I took a step back and started to check all collaboration platforms. These are the platforms that I used to try and find Jonathan's other online resources (emphasis on try):

- Instagram[x]
- Facebook[x]
- Youtube[x]
- Linkedin[x]

After checking those websites, I realized that the title had "Git" in it, so why not check GitHub? After a little bit of searching, I found [Jonathans GitHub page](https://github.com/j0nathanwither5). Now that we found the collaboration platform, we get to move on to version control.

To properly utilize version control, we need to look at the respository offered by Jonathan, myfirstprogram repository, that contains a README.md file and a helloworld.py file. When looking at the README.md file, we see that it has little to offer, all it says is that he wants to learn markdown. But looking at the helloworld.py file, we see that the file had an update sometime last year, perhaps we can look at the older version of it, and that is how we can properly utilize version-control.

Looking at the older version of helloworld.py brought me to [this page](https://github.com/j0nathanwither5/myfirstprogram/commit/4b45ede0c0cdebb5ecf8d4923a25b83e15f01b41) which contains the flag in the description.

### TL;DR
After finding Jonathans GitHub page, I searched through an older version of a helloworld.py file to find the HTB flag

### Flag
HTB{H1dd3n_d4t4_1n_pl4in_s1ghT???}

