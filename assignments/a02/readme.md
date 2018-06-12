# Homework Assignment 02 (due 6/13 12p)

This assignment is to be completed individually.  You are not allowed to share your answers with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or post those questions on [Piazza](https://piazza.com) using the appropriate folder tag.

> Do not use a computer for solving the questions below

## Number Representation (Signed Integers and Floating Point Numbers)

1. For each of the following integers, indicate their bit representation using 8 bits and two's complement.  If overflow happens, show the resulting bits and write *overflow* respectively:
   * -23
   * 45
   * 326
   * -129
   * 0
   * 127
   * 1
   * -1

2. Convert the following `float`s into their corresponding floating point numbers:
    * 11000001110110110000000000000000
    * 00011001000101100001000000000001
    * 01111111100000000000000000000000
    * 11111111100000000000000000000000
    * 00000000000000000000000000000000
    * 10000000000000000000000000000000
    * 00101010101010101000000000000000

3. Determine the output of the following (explain what happened):
```c
float x = 0.1;
float y = 0.1;
if (x + y == 0.2) {
    printf("Floats add fine\n");
} else {
    printf("Floats do not add fine\n");
}
```

## Data Types

1. Complete the following table:

data type            | min value | max value | number of bytes
---------------------|-----------|-----------|----------------
`unsigned char`      |           |           |
`signed char`        |           |           |
`unsigned short`     |           |           |
`signed short`       |           |           |
`unsigned int`       |           |           |
`signed int`         |           |           |
`unsigned long`      |           |           |
`signed long`        |           |           |
`unsigned long long` |           |           |
`signed long long`   |           |           |
`float`              |           |           |
`double`             |           |           |
`long double`.       |           |           |

2. Given an unsigned short `x`, with a current value of 65,000; what will the result of `x * 2` be? 

3. What is the result of `'\x63' + '\x40'` in C?

## Expressions

1. What is the value of the following statements:
   * `(1 == 1) - ((1 < 2) && 10) + (0 || (0 == 0))`
   * `(34 >> 2) + 2L - 0xAB`
   * `2 * 15 % 5 * 4 + (10 - 3) / (3 + 2)`
   * `(! (1 && 1)) && (0 | 7)`

2. Write logical expressions that can determine whether a given variable `a` of type `char` is:
   * an uppercase letter
   * a lowercase letter
   * a digit (from 0 to 9)
   * a whitespace (can be either a blank space or tab or a newline character)

3. Consider a variable `unsigned int var`; write expressions using bitwise operators to:
   * test whether at least three of the four most significant bits are on
   * reverse the byte order (e.g. 0x000CAFFE should produce 0xFEAF0C00)
   * rotate `var` four bits to the right (e.g. 0x000CAFFE should produce 0xE000CAFF)
   
4. Using precedence rules, evaluate the following statements, and determine the value of all the variables after running each line:
   * `x = 0xFF33; m = 0xFF00; c = x & m == 0;`
   * `x = 10; y = z = 2; z = y = x++ + ++y * 2;`
   * `x = 10; y = 4; z = 1; y >>= x & 0x2 && z;`
   * `int a = 1; int b = 1; int c = a || --b; int d = a-- && --b;`
   
## Submission and Grading

You will submit a **single PDF file** through [Gradescope](https://gradescope.com).

> You must be reminded that students caught cheating or plagiarizing will receive **no credit**.  Additional actions, including a failing grade in the class or referring the case for disciplinary action, may also be taken.

