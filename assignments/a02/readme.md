# Homework Assignment 02 (due 6/12 12p)

This assignment is to be completed individually.  You are not allowed to share your answers with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or post those questions on [Piazza](https://piazza.com) using the appropriate folder tag.

## Number Representation (show all related work)

1. In computer programming, the range of a datatype is constrained by how many bits that datatype uses. Provide the formula to calculate range given `n` bits.

2. Given 4 bits, what is the largest unsigned number you can represent?

3. If you added 1 to the number you found in the previous question, what would the result be?

4. For the following numbers, convert them into their binary representations, then use Two's Complement to negate them; your answer should list both the positive, and negative values.
    * 1
    * 4
    * 7
    * 10
    * 14

5. Convert the following problems to binary, then use *addition* to solve. (Convert subtraction into addition of the negative)
    * 5 - 5
    * 10 + 10
    * 13 - 4
    * 8 - 3

6. Determine the output of the following:
```c
float x = 0.1;
float y = 0.1;
if (x + y == 0.2) {
    printf("Floats add fine\n");
} else {
    printf("Floats do not add fine\n");
}
```

7. Convert the following `float`s into decimal.
    * 1 10000011 10110110000000000000000
    * 0 00110010 00101100001000000000001
    * 0 11111111 00000000000000000000000
    * 1 11111111 00000000000000000000000
    * 0 00000000 00000000000000000000000
    * 1 00000000 00000000000000000000000
    * 0 01010101 01010101000000000000000


## Data Types (show all related work)

1. Complete the following table:

data type            | min value | max value 	
---------------------|-----------|-----------	
`char`               |           |
`unsigned short`     |           |
`signed short`       |           |
`unsigned int`       |           |
`signed int`         |           |
`unsigned long`      |           |
`signed long`        |           |
`unsigned long long` |           |
`signed long long`   |           |

2. Given an unsigned 2-byte variable `x`, with a current value of 65,000; what will the result of `x * 2` be? 

3. What is the result of `'\x63' + '\x40'` in C?

4. Without using the `"` character, declare a variable s containing the string "World".

5. What is the value of the following statement: 
`(1 == 1) - ((1 < 2) && 10) + (0 || (0 == 0))`

6. Complete the following table:

data type | size | number of bits for exponent | number of bits for fraction
----------|------|-----------------------------|-------------------------------
`float`     |      |   |
`double`    |      |   |
`long double` (refer to the x86 extended precision format) |    |   |

