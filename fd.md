
## fd

### Challenge description:

    Mommy! what is a file descriptor in Linux?

    * try to play the wargame your self but if you are ABSOLUTE beginner, follow this tutorial link:
    https://youtu.be/971eZhMHQQw

    ssh fd@pwnable.kr -p2222 (pw:guest)



fd:

fd is kind of hint for file descriptor
we know fd of stdin is `0`, for in ordet ot reed the flag file in this statement we should pass `"LETMEWIN\n"` in stdin.

    if(!strcmp("LETMEWIN\n", buf)){
            printf("good job :)\n");
            system("/bin/cat flag");
            exit(0);
    }

for reading from stdin we should make `fd = 0`, and for this perpose we have:

	int fd = atoi( argv[1] ) - 0x1234;

the decimal value of 0x1234 is 4660 and `atoi( '4662' ) - 0x1234` would be `0`. so we have the flag:

![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/fd-1.png)
