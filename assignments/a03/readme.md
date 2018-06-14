# Homework Assignment 03 (due 6/20 12p)

This assignment is to be completed individually.  You are not allowed to share your code with other students.  The assignment is worth a total of 100 points.  If you have any questions, visit us during office hours and/or post those questions on [Piazza](https://piazza.com) using the appropriate folder tag.

1. Privileges.  This program should prompt the user for an age, and then output one of the following depending on the age given: "Too young!" for anyone under 16; "Can drive" for those between 16 and 18; "Can join the military" for those between 18 and 21; and finally "Can have a beer" for ages greater than or equal to 21. 

1. Addition.  Prompt the user for two numbers, then output the following string: `"<a> + <b> = <c>"` where `a` is the first number given, `b` is the second, and `c` is the sum.

1. Odd or Even.  This program reads an integer number from the user, and prints whether or not the provided number is even or odd.  The output should be a single line formatted as follows: `"<number> is <odd|even>"` where `number` is replaced by the user input, and `odd` or `even` is printed depending on whether or not the number is odd or even.  If the number is prime, the following text should be appended to the output: `" and prime"`.

1. Century from Year.  Given a year, this program should output the century it is in.  The first century spans from year 1 up to, and including, year 100.  The second spans years 101 through 200.  Do not use strings or arrays.  The year should be stored as an integer variable.

1. R2.  The number S is called the mean of two floating point numbers, R1 and R2, where S = (R1 + R2) / 2.  This program should prompt the user to provide R1 and S, then it should print R2 to the command line.

1. Countdown.  This program should ask for a number from the user, then print a countdown, from that number, to zero.  Each number should be printed on a new line.

1. Countdown 2.0.  Copy your countdown program, and modify it so that up to 10 numbers are printed on the same line. 
If given the number 10 as input, this program should output 2 lines, the first containing the numbers 10 through 1 separated by spaces, the second containing the number 0.

1. Multiples of 3 and 5.  This program should prompt the user for a number, it should then compute the sum of all the multiples of 3 or 5 below the given number.  If we list all the natural numbers below 10 that are multiples of 3 or 5, we get 3, 5, 6 and 9.  The sum of these multiples is 23.  If the user provided the number 10, the output would be 23.

1. Nth Fibonacci.  The Fibonacci sequence is defined as the series: 1, 1, 2, 3, 5, 8, 13, ... Your program should take a number N as input, and then return the Nth Fibonacci number.  If the user were to enter 4 for example, the program should output 3.

1. Quadrant Selection.  In mathematics, 2-dimensional cartesian systems can be segmented into four quadrants, depending on whether `x` and `y` are positive or negative. For example, given (1, 1) the program should output Quadrant 1.  Write a program that asks the user an `x`, and then a `y` coordinate, and then outputs what quadrant the point falls in.

1. Palindrome.  In English a palindrome is a word that is the same in reverse, as in "aabaa", which backwards is still "aabaa".  After prompting the user for a number to check, this program should output `"<number> <is|is not> a palindrome"` where `number` is the user provided positive integer, and `is` or `is not` gets printed depending on whether the number is a palindrome.

1. Basic Calculator.  This program will act as a basic calculator, by working in three steps.  First prompt the user for `a`, then the operator of their choosing, then `b`.  Once you have these three elements, output the result of the operation to the command line in the form `"<a> <operator> <b> = <c>"` where `c` is the resulting value.

1. Adding ASCII.  Write a program that reads a sequence of characters from the standard input, then computes the sum of each vowel the input sequence.  Print this sum to the command line.

1. Interval.  Write a program that reads a floating point number and prints `yes` if the number is in the interval [-1,1), and `no` otherwise.

1. Exp.  Write a program that reads an integer `n` and prints the value of `e`.  The value of `e` (Euler's number) is equal to the series: 1/0! + 1/1! + 1/2! + 1/3! + ... + 1/n!.   Your result should be displayed using 10 decimal places (pad zeros to the right if necessary).

1. Nested Loops 1.  Write a program that reads an integer `n` and generates the following output (example below shows `n=5`):
```
++++1
+++22
++333
+4444
55555
```

17. Nested Loops 2.  Write a program that reads an integer `n` and generates the following output (example below shows `n=5`):
```
++++1
+++2
++3
+4
5
```

18. Triangle.  Write a program that reads an integer `n`, which denotes the number of lines, and generates the following output (example below shows `n=4`):
```
1
2 3
4 5 6
7 8 9 10
```

19. Pyramid.  Write a program that reads an uppercase letter `ch`, and displays the following output (example below shows `ch=D`)
```
      A
    A B A 
  A B C B A
A B C D C B A 
```

### Submission and Grading
You will submit a *zip file* named `pa3.zip` through Gradescope.  Your zip archive must contain your source files **only**.  For each of the problems, create a file called `main_<num>.c` where num is the question number itself with no leading zeros.  Ensure *all* of your code resides within the `main()` function within that file.  All programs **must** compile and execute without warnings.  Your programs will be automatically graded.  For each of the questions you either pass the test cases (full points) or not (zero points).

> You must be reminded that students caught cheating or plagiarizing will receive `no credit`.  Additional actions, including a failing grade in the class or referring the case for disciplinary action, may also be taken.
