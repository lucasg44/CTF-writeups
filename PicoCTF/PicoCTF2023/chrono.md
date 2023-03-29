# Chrono

### Overview
This challenge was a General Linux skills challenge in PicoCTF 2023. I solved this challenge on my own.

### The problem
How to automate tasks to run at intervals on linux servers?

Additional details will be available after launching your challenge instance.

Server: saturn.picoctf.net
Port: 51858
Username: picoplayer 
Password: pKLLorPnnH
(This instance is expired by now)

### The solution
In order to get started, I authenticated into the server using
``````bash
ssh -p 51858 picoplayer@saturn.picoctf.net
``````

Using the password "pKLLorPnnH" I made my way into the server.

From there, I enumerated to see what I have privledges to see, until I made my way to the /home/challenges directory, which contained a file called metadata.json which I used a cat command to read the data. The data in metadata.json contained the flag.

### TL;DR
An unsecure file in the /home/challenges directory contained the flag.

### Flag
picoCTF{Sch3DUL7NG_T45K3_L1NUX_1b4d8744}
