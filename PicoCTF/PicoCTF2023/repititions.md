# Repititions

### Overview
This challenge is a cryptography challenge from PicoCTF 2023, I completed this challenge on my own.

### Resources
https://www.base64decode.org/

This website helped me decode the base64 code

### The problem
Can you make sense of this file? Download the [file](https://artifacts.picoctf.net/c/293/enc_flag).

(Hint) Multiple decoding is always good.

### The solution
After looking at the file, I realized this was a base64 code, which is provided below.
``````bash
VmpGU1EyRXlUWGxTYmxKVVYwZFNWbGxyV21GV1JteDBUbFpPYWxKdFVsaFpWVlUxWVZaS1ZWWnVh
RmRXZWtab1dWWmtSMk5yTlZWWApiVVpUVm10d1VWZFdVa2RpYlZaWFZtNVdVZ3BpU0VKeldWUkNk
MlZXVlhoWGJYQk9VbFJXU0ZkcVRuTldaM0JZVWpGS2VWWkdaSGRXCk1sWnpWV3hhVm1KRk5XOVVW
VkpEVGxaYVdFMVhSbFZhTTBKVVZGWmFWbVF4V1hoYVNHUlNDbUpXUmpOVVZscFhWbTFHZEdWRlZs
aGkKYlRrelZERldUMkpzUWxWTlJYTkxDZz09Cg==
``````

After decoding the repeated base64 codes 6 times over, it gave me the flag.

### TL;DR
Decoding the code for the base64 6 times over gave me the flag

### Flag
picoCTF{base64_n3st3d_dic0d!n8_d0wnl04d3d_0e8b0014}

