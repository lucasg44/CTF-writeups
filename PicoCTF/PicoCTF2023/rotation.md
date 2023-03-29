# Rotation

### Overview
This challenge is a cryptography challenge from PicoCTF 2023, I completed this challenge on my own.

### Resources
https://www.dcode.fr/rot-cipher

This website was able to pull the pico flag

### The problem
You will find the flag after decrypting this file Download the [encrypted flag](https://artifacts.picoctf.net/c/447/encrypted.txt).

(Hint) Sometimes rotation is right

### The solution
The txt file gave me the following
``````text
xqkwKBN{z0bib1wv_l3kzgxb3l_73l97nm4}
``````

With this, I plugged the code into the website above, I scrolled down to find the "[A-Z] + 8 rotation" category and it gave me the flag

### TL;DR
The resource showed me it was a rot cipher with "[A-Z] + 8 rotation" description.

### FLag
picoCTF{r0tat1on_d3crypt3d_73d97fe4}
