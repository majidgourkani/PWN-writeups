## flag

### Challenge description:

    Papa brought me a packed present! let's open it.
    Download : http://pwnable.kr/bin/flag
    This is reversing task. all you need is binary

There is no source code.So, this is a reverse engineering task.
file command:

    root@kali:~/Desktop/pwd/flag# file flag
    flag: ELF 64-bit LSB executable, x86-64, version 1 (GNU/Linux), statically linked, no section header

from extracting strings, we can see that it’s packed by UPX.
packers can do some kind of obfuscation on binary files.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/flag-1.png)

by searching on the internet, I found an upx unpacker (https://upx.github.io/).
i created a unpacked flag file:
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/flag-3.png)

Now, with `strings` command and -n option (Locate & print any NUL-terminated sequence), we can find the flag:
flag is here:
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/flag-2.png)
