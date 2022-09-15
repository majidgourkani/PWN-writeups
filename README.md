
# pwnable.kr Write ups

Here, I have written a write-up of some pwn challenges of pwnable.kr .


## bof

### Challenge description:

    Nana told me that buffer overflow is one of the most common software vulnerability. 
    Is that true?
    Download : http://pwnable.kr/bin/bof
    Download : http://pwnable.kr/bin/bof.c
    Running at : nc pwnable.kr 9000 '

It is a buffer overflow challenge. The vulnerable code is:
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/bof-1.png)

This code reads user input with `gets()` method, which is vulnerable to Buffer overflow and write it in a 32 bytes array.
gets() doesn’t do any size checking, and by overwriting a key we can get a shell.

with the gdb disassemble the function `func()`, we can see the address of the compare instruction that compares between the value of `key` and `0xcafebabe`.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/bof-2.png)

To overwrite the `key`, to reach the `ebp` we need 0x2c or 44 character + and than 4 bytes for ebp + 4 bytes for the ret.
now overwrite value `0xcafebabe` in the memory. now the condition would be pass successfully and we have a shell.
following python code would do that.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/bof-3.png)

flag is here: 
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/bof-4.png)

