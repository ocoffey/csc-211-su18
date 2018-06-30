# Homework Assignment 04 (due 7/3 12p)

This assignment is to be completed individually.  You are not allowed to share your code with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or create a post on [Piazza](https://piazza.com) using the appropriate folder tag.

1. `void mirror_image(char *s)`.  Create a function that takes a string `s`, then prints `s` both normally and in reversed order, separated by a `|` character.  The function should print exactly: `s|s'`, where `s` is the original string, and `s'` is the same string in reverse.  For example, if `s = "hello"`, then the output would be `hello|olleh`.

1. `void palindrome(char *s)`. Create a function that takes a parameter `s` and prints whether or not `s` is a palindrome.  The output should be `s <is|is not> a palindrome` where `<is|is not>` is determined by whether or not the string is a palindrome.  For example, if `s = "abcba"` then the output would be `abcba is a palindrome`.

1. `void array_builder(int *A, int len)`.  Create a function that takes an array of integers `A` and an integer `len>0` as parameters.  The function should then print all of the numbers in the array formatted as follows: `[A1, A2, ..., Alen]`.  Note the brackets, and the commas are all necessary.  If `len = 4`, and the array contains the numbers `11 12 30 4`, the output would be: `[11, 12, 30, 4]`.

1. `void safe_string(char *s)`.  Create a function that takes a string `s`, then prints that string with all invalid characters removed.  For this problem, all characters are invalid **except** lowercase English letters.  For example, if `s = "h3l10 W0r1D"`, the output would be `hlr`.

1. `void rotate_string(char *s, int n)`.  Create a function that takes a string `s` and an integer `n>0`.  The function should then print `s` rotated right by `n` characters to the right.  For example, given the string `"abc"` and `n = 1`, the function should print `"cab"`.

1. `char most_frequent(char *s)`.  Write a function that takes a string `s`, and returns the most frequent character in `s`.  For example, in the string `"aaabbc"` the most frequent character is `'a'` (break ties by chosing the leftmost character).

1. `void selective_filter(char *s1, char *s2)`.  Write a function that takes two strings `s1` and `s2`, and prints the first string, where all characters in the second string have been removed (case sensitive).  For example: given `"hello world"` and `"d owl"`, the output should be `"her"`, as characters `'d', ' ', 'o', 'w'`, and `'l'` have been removed.

1. `void palindrome_rearranging(char *s)`.  Write a function that takes a string `s`, then prints whether or not that string can be *rearranged* to form a palindrome.  For example "aabb" can be rearranged, thus it should print `"True"`. `"abca"` cannot be rearranged into a palindrome, thus it should print `"False"`.

1. `unsigned long any2dec(char *num, unsigned int b)`.  Write a function that returns the decimal integer number that corresponds to the number `num` (assume upper-case letters) in a given base `b, 1 < b <= 16`.

1. `void hex2rgb(char *hex)`.  Write a function that takes a string `hex`.  The parameter `hex` contains a hex color code.  Your function should convert the hex color code into a RGB value.  For example, if the input is `"#04F3A8"`, your function should print `"rgb(4,243,168)"` to the standard output.

1. `unsigned long diameter(int n, double *x, double *y)`.  Create a function that, given a finite set `P` of 2D points, calculates the floor of the largest (euclidean) distance between any two points of `P`.  The input to your function is the number of points `n > 1`, an array of `x` coordinates, and an array of `y` coordinates for each of the points.

1. `int pos_divisors(unsigned long a)`.  Create a function that takes an integer `a`, such that `1 < a < 10^10` and checks whether `a` and `a+1` have the same number of positive divisors.  For example 21 has 4 positive divisors {1, 3, 7, 21} and 22 has 4 positive divisors {1, 2, 11, 22}.  Your function will return 1 if `a` and `a+1` have the same number of positive divisors and 0 otherwise.

### Submission and Grading
You will submit a single file named `functions.c` through Gradescope.  If you eventually need to create additional functions, those should also be included in this file.  Questions will be automatically graded, therefore, you must use the same function prototypes provided in this assignment, otherwise the autograding tests for correctness will not work and you won't get credit.  For each of the questions you either pass the test cases (full points) or not (zero points).

> You must be reminded that students caught cheating or plagiarizing will receive `no credit`.  Additional actions, including a failing grade in the class or referring the case for disciplinary action, may also be taken.
