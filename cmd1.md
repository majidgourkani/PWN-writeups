## cmd1

### Challenge description:

    Mommy! what is PATH environment in Linux?

    ssh cmd1@pwnable.kr -p2222 (pw:guest)

from the source code, we can realize that the following code will change the `PATH` environment and we don't have access to the `cat` or other commands of bash.

    `putenv("PATH=/thankyouverymuch");`
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/cmd1-1.png)

so I tried to give `/bin/cat /home/cmd1/flag` as input, 
but, `flag` string is filtered. so I tried to cat all the files in this directory with `/bin/cat /home/cmd1/*` input.

we can see the flag in the last line.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/cmd1-2.png)
