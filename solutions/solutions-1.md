# Homework Assignment 02 (due 6/13 12p)

This assignment is to be completed individually.  You are not allowed to share your answers with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or post those questions on [Piazza](https://piazza.com) using the appropriate folder tag.

> Do not use a computer for solving the questions below

## Number Representation (Signed Integers and Floating Point Numbers)

1. For each of the following integers, indicate their bit representation using 8 bits and two's complement.  If overflow happens, show the resulting bits and write *overflow* respectively:
   * -23 -> 11101001
   * 45 -> 00101101
   * 326 -> 01000110 **overflow**
   * -129 -> 00000000 **overflow**
   * 0 -> 00000000
   * 127 -> 01111111
   * 1 -> 00000001
   * -1 -> 11111111

2. Convert the following `float`s into their corresponding floating point numbers:
    * 1 10000011 10110110000000000000000 -> -1.7109 * 2^4 = -27.375
    * 0 00110010 00101100001000000000001 -> 1.17236 * 2^-77 = 7.75805 * 10^-24
    * 0 11111111 00000000000000000000000 -> Positive Infinity
    * 1 11111111 00000000000000000000000 -> Negative Infinity
    * 0 00000000 00000000000000000000000 -> Positive Zero
    * 1 00000000 00000000000000000000000 -> Negative Zero
    * 0 01010101 01010101000000000000000 -> 1.3320 * 2^-42 = 3.028688 * 10^-13

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

> Floats do not add fine.

## Data Types

1. Complete the following table:

data type            | min value | max value | number of bytes
---------------------|-----------|-----------|----------------
`unsigned char`      | 0 | 255 | 1
`signed char`        | -127 | 127 | 1
`unsigned short`     | 0 | 65,535 | 2
`signed short`       | -32,768 | 32,767 | 2
`unsigned int`       | 0 | 4,294,967,295  | 4
`signed int`         | -2,147,483,648 | 2,147,483,647 | 4
`unsigned long`      | 0 | 18,446,744,073,709,551,615|8
`signed long`        | -9,223,372,036,854,775,808 | 9,223,372,036,854,775,807 |8
`unsigned long long` | 0 | 340,282,366,920,938,463,463,374,607,431,768,211,455 | 16
`signed long long`   | −170,141,183,460,469,231,731,687,303,715,884,105,728 | 170,141,183,460,469,231,731,687,303,715,884,105,727 | 16
`float`              | -(1-2^-24) * 2^128 | (1-2^-24) * 2^128 | 4
`double`             | -(1-2^-53) * 2^102 | (1-2^-52) * 2^102 | 8
`long double`.       | -Infinity | +Infinity | 16

2. Given an unsigned short `x`, with a current value of 65,000; what will the result of `x * 2` be? 

> 63,392

3. What is the result of `'\x63' + '\x40'` in C?

> '0xa3'

## Expressions

1. What is the value of the following statements:
   * `(1 == 1) - ((1 < 2) && 10) + (0 || (0 == 0))` = 1
   * `(34 >> 2) + 2L - 0xAB` = -161
   * `2 * 15 % 5 * 4 + (10 - 3) / (3 + 2)` = 1.4
   * `(! (1 && 1)) && (0 | 7)` = 0

2. Write logical expressions that can determine whether a given variable `a` of type `char` is:
   * an uppercase letter = `a >= 65 && a <= 90`
   * a lowercase letter = `a >= 97 && a <= 122`
   * a digit (from 0 to 9) = `a >= 48 && a <= 57`
   * a whitespace (can be either a blank space or tab or a newline character) `(a == 32) || (a == 9) || (a == 10)`

3. Consider a variable `unsigned int var`; write expressions using bitwise operators to:
   * test whether at least three of the four most significant bits are on `!!(var & 1 << 31) + !!(var & 1 << 30) + !!(var & 1 << 29) + !!(var & 1 << 28) >= 3` 
   * reverse the byte order (e.g. 0x000CAFFE should produce 0xFEAF0C00)
   * rotate `var` four bits to the right (e.g. 0x000CAFFE should produce 0xE000CAFF) `(var >> 4) | (var << 27)`
   
4. Using precedence rules, evaluate the following statements, and determine the value of all the variables after running each line:
   * `x = 0xFF33; m = 0xFF00; c = x & m == 0;` -> `x = 0xFF33; m = 0xff00; c = 0xFF33 (which is x)`
   * `x = 10; y = z = 2; z = y = x++ + ++y * 2;` -> `x = 11; y = 16; z = 16;`
   * `x = 10; y = 4; z = 1; y >>= x & 0x2 && z;` -> `x = 10; y = 4; z = 1;`
   * `int a = 1; int b = 1; int c = a || --b; int d = a-- && --b;` -> `a = 0; b = -1; c = 1; d = 1`
   
## Submission and Grading

You will submit a **single PDF file** through [Gradescope](https://gradescope.com).

> You must be reminded that students caught cheating or plagiarizing will receive **no credit**.  Additional actions, including a failing grade in the class or referring the case for disciplinary action, may also be taken.

