## bof

### Challenge description:

    Mommy! I made a lotto program for my homework.
    do you want to play?

    ssh lotto@pwnable.kr -p2222 (pw:guest)



from the source code, we know it will receive 6 6-character from user input. 
`man read`
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/lotto-1.png)

and generate a 6-character random string, with char code between 1 to 45.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/lotto-2.png)

in this part, the code attempt to count the number of matches in the random and user input strings. instead of comparing each chare one-by-one, it will compare each random character with all the characters of the user input string.
so if all the characters of the user input string are the same, and be the same as one character in the random string, the below condition will be passed and we will have the flag.
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/lotto-3.png)


flag is here: 
![App Screenshot](https://github.com/majidgourkani/PWN-writeups/blob/main/images/lotto-4.png)
