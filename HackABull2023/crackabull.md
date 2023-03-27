# Crack-a-bull

### Overview
Crack-a-bull was an 125 point general skills challenge at Hack-a-bull 2023. This challenge was solved on March 25th at 5:08 PM. This challenge was created by Jacob H.

### Resources
For this challenge, I prioritized the use of john the ripper on the linux command terminal.

### The problem
Just last week we hired a new intern who said he could crack any hash. Sadly, we fired him for installing some cryptic cat memes on his work computer. Are you able to crack this uncommon hash we haven't used before?

Hint: Faster than MD5, SHA-1, SHA-2, and SHA-3, yet is at least as secure as the latest standard SHA-3

Download the file [here](https://ctf.hackabull.dev/files/71633ea321c888e581f0b9e6dc009e18/enc?token=eyJ1c2VyX2lkIjoxNCwidGVhbV9pZCI6NSwiZmlsZV9pZCI6MjN9.ZCHD0A._t6rw4r6qDFgDSwAokbGTO7D4_E)

### The solution
The hash that we are provided with in the very beginning is posted below:
``````text
59ce0d664459b880f94e5a63548bc4efde3f4f2809f0daf6a9df45ceaf73e19b3bb14acbe36593ce564f202ca0bc585bc92ba8bcf86add3f4baa0386fb7d8600
``````

Using the hint provided, we realized that the file was encoded in a "Blake2" format. In order to properly decode the blake2 format, we utilized john the ripper.
``````text
john enc --format=raw-blake2
``````
After letting john run for a little, it returned a code named "thuglife", which we plugged into the flag format to complete the challenge

### TL;DR
Using john the ripper helped me doce the blake2 format for the hashed password

### Flag
WCSC_HackaBull23{thuglife}
