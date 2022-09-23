
## cmd2

### Challenge description:

    Daddy bought me a system command shell.
    but he put some filters to prevent me from playing with it without his permission...
    but I wanna play anytime I want!

    ssh cmd2@pwnable.kr -p2222 (pw:flag of cmd1)

this is just like the cmd1. the path environment variable will be deleted by:

    delete_env();
    putenv("PATH=/no_command_execution_until_you_become_a_hacker");

![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/cmd2-1.png)

also there are some more filters here. we can not use `/`.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/cmd2-2.png)

as our command run in the `sh`, so we should use a built-in commands of sh. from the `man sh` page, I realized that the `command` with `-p` switch can can run other command such as `cat`.
and the flag is filtered. so I tried to bypass the flag with `\”f\”\”l\”\”a\”\”g\”`.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/cmd2-3.png)

so now again we can use: `./cmd2 “command -p cat \”f\”\”l\”\”a\”\”g\””`
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/cmd2-4.png)
