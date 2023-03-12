# Signature Leaks

### Overview
This challenge was a OSINT challenge as a part of CyberHack 2023, I solved this challenge completely on my own. This challenge was rated an easy challenge on Hackthebox.

### The Problem
Jonathan tends to leak information in his email replies.

### The Solution
Following the instructions yet again, we figure out that we need to find the email for Jonathan. Lucky for us, the email is found in the description of his [twitter](https://twitter.com/j0nathanwither5) profile.

After viewing the email, I realized that all I need to do is send an email and see if there will be an automated reply. So I sent an email to the email that was provided:
jonathanwitherson@gmail.com

About 5 minutes later I got a reply. The reply stated that he wanted me to take care of a secret password key, which was actually just the HTB flag.

### TL;DR
I sent an email to jonathanwitherson@gmail.com from the twitter description. Jonathan replied with the HTB flag.

### Flag
HTB{yoUr_em41l_maY_p0s3_4_r1sK}
