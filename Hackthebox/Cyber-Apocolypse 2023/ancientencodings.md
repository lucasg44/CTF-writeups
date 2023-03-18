# Ancient encodings

### Overivew
This challenge was rated very easy for HTB cyber apocolypse. This challenge was a cryptography challenge. I completed this on my own

### Resources
This will be revealed at the end of Cyber-apocolypse

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

The rest will be revealed at the end of Cyber-apocolypse 2023
