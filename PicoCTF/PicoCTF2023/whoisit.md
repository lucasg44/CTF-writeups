# Who is it

### Overview
This challenge is a forensics challenge from PicoCTF 2023, I completed this challenge on my own.

### Resources
https://whois.domaintools.com/173.249.33.206

This website helped me pull the name.

### The problem
Someone just sent you an email claiming to be Google's co-founder Larry Page but you suspect a scam. Can you help us identify whose mail server the email actually originated from? Download the email file [here](https://artifacts.picoctf.net/c/363/email-export.eml). 
Flag: picoCTF{FirstnameLastname}

(Hint) whois can be helpful on IP addresses also, not only domain names.

### The solution
In order to get started, I analyzed the file until I saw the IP address from the sender. 
``````text
173.249.33.206
``````
I took the IP address and plugged it into the resource above, from there I scrolled until I saw the name and set it up on the flag format.

### TL;DR
I used whois to search the IP address of the sender and pulled the name

### Flag
picoCTF{WilhelmZwalina}
