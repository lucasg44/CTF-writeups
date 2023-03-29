# FindMe

### Overview
This challenge was a web exploit challenge on PicoCTF 2023. I completed this challenge on my own.

### The problem
Help us test the form by submiting the username as test and password as test!

Additional details will be available after launching your challenge instance.
(Hint) Any redirectories?

### The solution
After authenticating into the website, I went into the login page and logged in with username:test and password:test!

After logging in I noticed something strange, the website stopped by two blank pages in a matter of seconds before actually hitting the home page.

I navigated back to the two blank pages I saw with the help of the hint, and I noticed this unique URLs:
``````text
(http://saturn.picoctf.net:59008/next-page/id=cGljb0NURntwcm94aWVzX2Fs)
(http://saturn.picoctf.net:59008/next-page/id=bF90aGVfd2F5X2QxYzBiMTEyfQ==) 
``````
I noticed that both of the ID's combined would get a base64 code, so I combined the ID's and got the flag

### TL;DR
After logging in, I noticed the website redirected itself and showed us two parts of a base64 encoded flag.

### Flag
picoCTF{proxies_all_the_way_d1c0b112}
