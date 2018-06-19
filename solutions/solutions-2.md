# Solutions to Homework Assignment 01 (due 6/5 12p)

This assignment is to be completed individually.  You are not allowed to share your answers with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or post those questions on [Piazza](https://piazza.com) using the appropriate folder tag.

## Basic Shell commmands

1. Provide a sequence of Bash commands that will:
    * go to your default home directory;
    * create a directory `test`;
    * rename `test` to `myproject`;
    * enter the directory `myproject`;
    * create a new empty file `main.c`; 
    * list all files in `myproject`, including hidden files;
    * return to the parent directory.

```bash
cd ~ && mkdir test && mv test myproject && cd myproject && touch main.c && ls -a && cd .. 
```
  
2. Provide a sequence of Bash commands that will:
    * go to your default home directory;
    * remove the directory `myproject`.

```bash
cd ~ && rm -rf myproject
```

3. Provide a sequence of Bash commands that will:
    * create files `a.txt`, `b.txt`, and `c.txt`;
    * write the line `a: 1 2 3 4 5` to `a.txt`;
    * write the line `b: 6 7 8 9 10` to `b.txt`;
    * write the line `a: 11 12 13 14 15` to `c.txt`;
    * concatenate `a.txt`, `b.txt`, and `c.txt` into `all.txt`

```bash
echo "a: 1 2 3 4 5" > a.txt && echo "b: 6 7 8 9 10" > b.txt && echo "a: 11 12 13 14 15" > c.txt && cat a.txt >> cat b.txt >> cat c.txt > all.txt
```
  
4. Create a file named `math.txt` with the following contents:
```text
1 + 1
2 * 2
2 ^ 0
2 ^ 16
2 ^ 32
20 / 3
16 / 0
```
Using `stdin` and `stdout` redirections, write shell commands that will process `math.txt` with the `bc` utility and save the output to `results.txt`

```bash
cat math.txt | bc 2> /dev/null > results.txt
```

5. Using the following commands (`ps`, `wc`), write a pipeline that will output how many processes are currently running

```bash
ps --no-headers | wc -l
```

6. Using the following commands (`history`, `grep`, `wc`), write a pipeline that will output how many times `ls` appears in your history

```bash
history | grep 'ls' | wc -l
```

7. Using the following commands (`find`, `wc`), write a pipeline that will output how many files ending with `.txt` exist on your entire filesystem.  Also, suppress the error messages by redirecting the `stderr` to `/dev/null`

```bash
find ~ -type f -name "*.txt"
```

8. Create a bash script file that will output `Hello CSC 211` to the `stdout` followed by a line indicating the number of files in the current directory (not including hidden files)

```bash
echo "Hello CSC 211"
echo ls | wc -l
```

## Number Systems

1. Convert the following binary numbers to decimals (show your work):
    * 1010010010010000 -> 42128
    * 0001000101010001 -> 4433
    * 1001010100001100 -> 38156
    * 0001010101011011 -> 5467

2. Convert the binary numbers from the previous exercise to hexadecimals (show your work).
    * 0xa490
    * 0x1151
    * 0x950c
    * 0x155b

3. Convert the binary numbers from the previous exercise to octals (show your work).
    * 122220
    * 10521
    * 112414
    * 12533

4. Convert your Student ID number to hexadecimal representation.  Hint: convert to binary, and then, to hexadecimal. (show your work)

5. Convert your phone number (including your area code) to hexadecimal representation.  Assume all digits in your phone number compose a single integer in decimal representation. (show your work)

6. Perform the following additions (show your work)
    * add 10001 to 00111 -> 11000
    * add 01111 to 10001 -> 10000
    * add 10111 to 10001 -> 101000
    * add 11111 to 10001 -> 110000

7. Perform the following subtractions (show your work)
    * subtract 0100 from 1000 -> 100
    * subtract 1001 from 11000 -> 1111
    * subtract 10111 from 110000 -> 11001
    * subtract 00111 from 10000 -> 1001

8. Assuming decimal numbers, indicate the result of the following operations (show your work):
    * 17 << 1 = 34
    * 28 << 3 = 224
    * 16 >> 1 = 8
    * 44 >> 2 = 11
    * 46 & 78 = 14
    * 255 & 33 = 33
    * 255 | 201 = 255
    * 28 | 13 = 29
    * (~73 & (18 << 1)) ^ (64 >> 2) = 52
    * (~28 | (33 >> 2)) & (41 ^ 128) = 169

## Submission and Grading

You will submit a **single PDF file** through [Gradescope](https://gradescope.com).

> You must be reminded that students caught cheating or plagiarizing will receive **no credit**.  Additional actions, including a failing grade in the class or referring the case for disciplinary action, may also be taken.
