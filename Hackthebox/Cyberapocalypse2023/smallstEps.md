# Small StEps

### Overivew
This challenge was rated very easy for HTB cyber Apocalypse. This challenge was a cryptography challenge.

### Resources
https://github.com/RsaCtfTool/RsaCtfTool

This tool is a brute forcing RSA decrypting tool that took in the values and gave me the flag

### The Problem
As you continue your journey, you must learn about the encryption method the aliens used to secure their communication from eavesdroppers. The engineering team has designed a challenge that emulates the exact parameters of the aliens' encryption system, complete with instructions and a code snippet to connect to a mock alien server. Your task is to break it.

### The Solution
We are given two files, the first one is labeled server.py
``````python
from Crypto.Util.number import getPrime, bytes_to_long

FLAG = b"HTB{???????????????}"
assert len(FLAG) == 20


class RSA:

    def __init__(self):
        self.q = getPrime(256)
        self.p = getPrime(256)
        self.n = self.q * self.p
        self.e = 3

    def encrypt(self, plaintext):
        plaintext = bytes_to_long(plaintext)
        return pow(plaintext, self.e, self.n)


def menu():
    print('[E]ncrypt the flag.')
    print('[A]bort training.\n')
    return input('> ').upper()[0]


def main():
    print('This is the second level of training.\n')
    while True:
        rsa = RSA()
        choice = menu()

        if choice == 'E':
            encrypted_flag = rsa.encrypt(FLAG)
            print(f'\nThe public key is:\n\nN: {rsa.n}\ne: {rsa.e}\n')
            print(f'The encrypted flag is: {encrypted_flag}\n')
        elif choice == 'A':
            print('\nGoodbye\n')
            exit(-1)
        else:
            print('\nInvalid choice!\n')
            exit(-1)


if __name__ == '__main__':
    main()
``````

We are also given solver.py
``````python
# This script is not necessary for the challenge but may be useful in the
# future.
from pwn import *


# This function takes in binary data and converts it to ASCII.
def toAscii(data):
    return data.decode().strip()


# This function sends the string "E" to the server and retrieves the public key
# and encrypted flag that are returned. The public key consists of two parts:
# N and e.
def choiceE():
    r.sendlineafter(b"> ", b"E")
    r.recvuntil(b"N: ")
    N = eval(toAscii(r.recvline()))
    r.recvuntil(b"e: ")
    e = eval(toAscii(r.recvline()))
    r.recvuntil(b"The encrypted flag is: ")
    encrypted_flag = eval(toAscii(r.recvline()))
    return N, e, encrypted_flag


# This function serves as the main logic of the solver script. It calls
# `choiceE()` to retrieve the public key and encrypted flag and prints them.
def pwn():
    N, e, encrypted_flag = choiceE()
    print(N, e, encrypted_flag)


# This block handles the command-line flags when running `solver.py`. If the
# `REMOTE` flag is set, the script connects to the remote host specified by the
# `HOST` flag. Otherwise, it starts the server locally using `process()`.
if __name__ == "__main__":
    if args.REMOTE:
        ip, port = args.HOST.split(":")
        r = remote(ip, int(port))
    else:
        r = process(["python3", "server.py"])

    pwn()
``````

When completing this challenge, I used the python3 command to request a response from the IP:
``````bash
python3 solver.py REMOTE HOST=139.59.178.162:32765
``````

Using the python3 code gave me values for N,E, and the encrypted text

- N = 11025402345224991321735865715277800393342588350521493814751530118552378356817150657169702902763910860823073431232385620436976602755030767806230924000127753
- E = 3
- Encrypted text = 70407336670535933819674104208890254240063781538460394662998902860952366439176467447947737680952277637330523818962104685553250402512989897886053

After this I plugged in the numbers to the RsaCtfTool to get the flag using the following command
``````bash
python3 RsaCtfTool.py -n 11025402345224991321735865715277800393342588350521493814751530118552378356817150657169702902763910860823073431232385620436976602755030767806230924000127753 -e 3 --uncipher 70407336670535933819674104208890254240063781538460394662998902860952366439176467447947737680952277637330523818962104685553250402512989897886053
``````

### TL;DR
I used RsaCtfTool to plug in the numbers for N,E, and encrypted text to brute force the flag

### Flag
HTB{5ma1l_E-xp0n3nt}

