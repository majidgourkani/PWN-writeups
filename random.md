## random

### Challenge description:

    Daddy, teach me how to use random value in programming!
    ssh random@pwnable.kr -p2222 (pw:guest)

source code is:
![alt text](https://github.com/majidgourkani/PWN-writeups/blob/main/images/random-1.png)

in this challange, rand() method is insecure for random number generation.
If we forgot to provide the rand() function with a seed, we got the same value every time. the default seed is 1.
generating a random number with rand() method, showed us that the vaule of random value is: 1804289383

![alt text](https://github.com/majidgourkani/PWN-writeups/blob/main/images/random-2.png)

XOR of (key ^ random) should become 0xdeadbeef. so by XORing the random and 0xdeadbeef we can reach the key.

![alt text](https://github.com/majidgourkani/PWN-writeups/blob/main/images/random-3.png)

so, the flag is here:

![alt text](https://github.com/majidgourkani/PWN-writeups/blob/main/images/random-4.png)
