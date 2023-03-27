# Ancient encodings

### Overivew
This challenge was rated very easy for HTB cyber Apocalypse. This challenge was a cryptography challenge. I completed this on my own

### Resources
This will be revealed at the end of Cyber-Apocalypse

### The problem
Your initialization sequence requires loading various programs to gain the necessary knowledge and skills for your journey. Your first task is to learn the ancient encodings used by the aliens in their communication. 

### The solution

This challenge contained two files, first one labeled output.txt
``````text
0x53465243657a467558336b7764584a66616a4231636d347a655639354d48566664326b786246397a5a544e66644767784e56396c626d4d775a4446755a334e665a58597a636e6c33614756794d33303d
``````

The second one labeled source.py
``````python
from Crypto.Util.number import bytes_to_long
from base64 import b64encode

FLAG = b"HTB{??????????}"


def encode(message):
    return hex(bytes_to_long(b64encode(message)))


def main():
    encoded_flag = encode(FLAG)
    with open("output.txt", "w") as f:
        f.write(encoded_flag)


if __name__ == "__main__":
    main()
``````

I realized the text was hexidecimal, so I decoded it to get a base64 code. After decoding the base64 code I got the flag

### TL;DR
I decoded a hex code to get base 64 and then decoded the base64 to get the flag

### Flag
HTB{1n_y0ur_j0urn3y_y0u_wi1l_se3_th15_enc0d1ngs_ev3rywher3}
