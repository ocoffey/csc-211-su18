# Homework Assignment 03 (due 6/19 12p)

This assignment is to be completed individually.  You are not allowed to share your answers with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or post those questions on [Piazza](https://piazza.com) using the appropriate folder tag.

## Programming

For all of the following problems, create a file called `main_<num>.c` where num is the question number itself, ensure *all* of your code resides within the `main()` function within that file. All programs **must** compile and execute without warnings, and ensure that the user prompt appears on it's own line upon termination.

1. Hello User! Create a program that asks the user to provide their name, then prints the line `"Hello <user>"` to the terminal, where `user` is replaced by the provided name.

2. Privileges. This program should prompt the user for an age, and then output one of the following depending on the age given: "Too young!" for anyone under 16; "Can drive" for those between 16 and 18; "Can join the military" for those between 18 and 21; and finally "Can have a beer" for ages greater than or equal to 21. 

3. Addition. Prompt the user for two numbers, then output the following string: `"<a> + <b> = <c>"` where `a` is the first number given, `b` is the second, and `c` is the sum.

4. Odd or Even. This program takes user input, and prints whether or not the provided number is even or odd. The output should be formatted as follows: `"<number> is <odd|even>"` where number is replaced by the user input, and odd or even is printed depending on whether or not the number is odd or even.

5. Century from Year. Given a year, this program should output the century it is in. The first century spans from year 1 up to, and including, year 100. The second spans years 101 through 200.

6. R2. The number S is called the mean of two numbers, R1 and R2, where S = (R1 + R2)/2. This program should prompt the user to provide R1 and S, then it should print R2 to the command line.

7. Countdown. This program should ask for a number from the user, then print a countdown, from that number, to zero. Each number should be printed on a new line.

8. Countdown 2.0. Copy your countdown program, and modify it so that up to 10 numbers are printed on the same line. 
If given the number 10 as input, this program should output 2 lines, the first containing the numbers 10 through 1 separated by spaces, the second containing the number 0. Ensure that the 0 character in this example is on it's own line, and that the prompt resumes on the line following.

9. Multiples of 3 and 5. This program should prompt the user for a number, it should then compute the sum of all the multiples of 3 or 5 below the given number. 
If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 4, 6 and 9. The sum of these multiples is 23. If the user provided the number 10, the output would be 23.

10. Nth Fibonacci. The Fibonacci sequence begins as follows: 1, 2, 3, 5, 8, 13, ... Your program should take a number as input, and then return the Fibonacci term corresponding to that number. 
If the user were to enter 2 for example, the program should output 3. *Remember that the sequence starts at index 0*

11. Quadrant Selection. In mathematics, graphs can be segmented into four quadrants, depending on whether `x` and `y` are positive or negative. For example, given (1, 1) the program should output Quadrant 1. This program should prompt the user for an `x`, and then a `y` coordinate. Once the program has both coordinates, it should output what quadrant the point falls in.

12. Palindrome. In English a palindrome is a word that is the same in reverse, as in "aabaa", which backwards is still "aabaa". After prompting the user for a string to check, this program should output `"<word> <is|is not> a palindrome"` where `word` is the user provided word, and `is` or `is not` gets printed depending on whether the word is a palindrome. 

13. Common Character Count. After prompting the user for two strings, output the number of characters in common the strings have. For `string1 = "aabcc"` and `string2 = "adcaa"` the output should be `3`, because they share 2 'a' characters, and 1 'c' character.

14. Basic Calculator. This program will act as a basic calculator, by working in three steps. First prompt the user for `a`, then the operator of their choosing, then `b`. Once you have these three elements, output the result of the operation to the command line in the form `"<a> <operator> <b> = <c>"` where `c` is the resulting value.

15. Clean output. Prompt the user for a string, then, print each lowercase English letter to the command line. For example, given the string "1234hello(()!u$$s%er)" the output should be "hellouser".
