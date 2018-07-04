# Homework Assignment 05 (due 7/10 12p)

This assignment is to be completed individually.  You are not allowed to share your code with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or create a post on [Piazza](https://piazza.com) using the appropriate folder tag.

The focus of this assignment is *recursion*, as such, you **must** solve each of the following using recursion. 

1. `int list_sum(int* arr, int n)`. Create a function that takes an integer array of length `n` that returns the summation of every element. For example, given the array `[1, 2, 3, 4, 5]` with `n=5`, function should return `15`.

1. `int is_palindrome(char* s)`. Create a function that takes an array of characters, and returns 1 if the array is a palindrome, 0 otherwise.

1. `int list_min(int* arr, int n)`. Create a function that returns the minimum of a given array of integers with length equal to `n`. Given the array: `[1, 4, 7, 2, 0]`, and `n=5`; the function should return 0.

1. `int list_max(int* arr, int n)`. Create a function that returns the maximum of a given array of integers with length equal to `n`.

1. `int multiply(int a, int b)`. Create a function that returns the product of two given integers. This function **cannot** use the `*` operator.

1. `void draw_triangles(int a, int b, int c)`. Create a function to print triangles to `stdout` that takes three positive integers: `a`, `b`, and `c` as input. The function should print the `'+'` character `a` times, then `a + c` times, then `a + c + c` times, and so on. This pattern should repeat until the line is `b` characters long. At which point, the pattern is repeated backwards. For example, calling `draw_triangle(4, 7, 1)` will output:
```c++
++++
+++++
++++++
+++++++
+++++++
++++++
+++++
++++
```
Where the first line is 4 characters long, the second 5, and so on; until the line is 7 characters long. 

1. `int atoi(char* s)`. Recreate the functionality of `atoi` by creating a function that takes an array of characters, such as "123", and returns the equivalent integer value, `123` in this case. 

1. `int is_in(char* s, char c)`. Create a function that searches for character `c` in string `s`, if the function finds `c` it should return 1. Otherwise, it should return 0.

1. `int len(char* s)`. Create a function that calculates the length of a given string. 

1. `void strcpy(char* a, char* b)`. Create a function that copies the contents of the character array `a` into the character array `b`. When this function is called, both `a` and `b` should be of equal length. 

1. `int sum_digits(int a)`. Create a function that returns the sum of the digits of the given number `a`. For example, if `a = 123`, then the output would be `6`.

1. `int strictly_increasing(int* arr)`. Create a function that returns 1 if the given array is strictly increasing, 0 otherwise. 

1. `int factorial(int n)`. Create a function that returns the factorial of `n`.

1. `void reverse(char* c)`. Create a function that prints the reverse of `c` to `stdout`. 

1. `int gcd(int a, int b)`. Create a function that returns the greatest common denominator between `a` and `b`. 

### Submission and Grading
You will submit a single file named `functions.c` through Gradescope.  If you eventually need to create additional functions, those should also be included in this file.  Questions will be automatically graded, therefore, you must use the same function prototypes provided in this assignment, otherwise the autograding tests for correctness will not work and you won't get credit.  For each of the questions you either pass the test cases (full points) or not (zero points).

> You must be reminded that students caught cheating or plagiarizing will receive `no credit`.  Additional actions, including a failing grade in the class or referring the case for disciplinary action, may also be taken.
