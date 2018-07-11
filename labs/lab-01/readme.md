# Pointers->get_excited()

In this lab you will use `debug50` to understand how pointers work when working with arrays.  It is particularly important that you have a good handle on pointers and how they work since nearly all of the data structures that we will be creating use pointers.

## 1. Getting Started

### 1.1 Compiling

Ensure that your terminal is in the same directory as the `main.c` file and then compile your program using the command: `gcc -std=c99 -g main.c -o main`.  The program should compile without errors.

This program takes no arguments so the command is `./main`

Make sure your program runs without errors before proceeding.

### 1.2 Set a Breakpoint at Line 7

On the left side of your `cs50ide` screen you should see line numbers.  Click just to the left of the line `7` to create a breakpoint, a red circle should appear.

### 1.3 Starting the debugger

To start your debugger, run:

```bash
$ debug50 main
```

## 2. Declaring and Setting an `int` and `int *`

At each stage we will look at the source code, step through the code, and print out the variables.

```C
// Declare an int variable, assign it the value 5
int number = 5;

// Declare a pointer to an int and set it to the address of number
int *numberPtr = &number;
```
The first line of the program in `main()` declares an `int` called `number` and sets it to the value `5`.  After setting a breakpoint at line `7` and running your program in `debug50` you should pause at the first line of code in `main()`.

> **Question 1:** When you pause at line `7` you should be able to see the value of `number` listed in the debug menu on the right.  What is the value of `number` so far?  Why is it this value?

> **Question 2:** Step through line `7` only once using the step button located just next to the play button in the debug menu (reads "step over" when you hover your mouse over it) and inspect the value of `number` again.  What is the value of `number` now?  Why did it change?

Since you stepped through your code only once so far, you should be at line `10`, the second line of code in `main()`.  Line `10` declares an `int *` called `numberPtr` and sets it to the address of `number` using the ***address-of operator:*** `&`, which is used when ***referencing*** a variable to get its memory address.

> **Question 3:** When you pause at line `10` inspect the value of `numberPtr`.  What is the value of `numberPtr` so far?  Why is it this value?

> **Question 4:** Step through line `10` only once using `step` and inspect the value of `numberPtr` again.  What is the value of `numberPtr` now?  Why did it change?

## 3. Change the value of `number` by dereferencing the pointer

```C
// Change the value of number using the pointer
*numberPtr = 10;
```

**Dereferencing** a pointer uses the memory address of the element pointed to and directly accesses the element so it can be updated.

> **Question 5:** Step through the code using the command "step over" button until you reach line `17`.  Inspect the value of number, and step over once more. What is the value of number now?

**BEFORE PROCEEDING**: Let's get out of our debugging session so we can set a new breakpoint.  Either press the play button to let the program run to completion, or click on the terminal and press Control-C.  Next, delete your breakpoint at line `7` by clicking on the red circle you created earlier.

Now set a breakpoint at line `34` and type `debug50 main` to run the program again.  You should pause at line `34`.

## 4. Declaring and instantiating an array on the stack and on the heap using `int *`

The next two declarations create an array on the stack, and an array on the heap.

> You may want to read [this pdf](http://cslibrary.stanford.edu/102/PointersAndMemory.pdf) regarding stack, heap, and memory allocation to familiarize yourself with this topic. Section 1 is simply an introduction to pointers, so you may skip it if you would like, but sections 2 through 4 contain information that is important in understanding how pointers work. You need not do any of the "Extra Optional Material" problems, although they may be used as extra practice in your free time.

```C
// Declare an int array on the stack
int array_on_stack[number];
printf("The address of array_on_stack is: %p", array_on_stack);

// Declare an int array on the heap
int *array_on_heap = (int *) malloc(sizeof(int) * number);
printf("The address of array_on_heap is: %p", array_on_heap);

// Set each element of array_on_heap
for (int i = 0; i < number; i++)
{
	array_on_heap[i] = i;
}
```

> **Question 6:** What are the values of `array_on_stack` and `array_on_heap`?  (`debug50` will not show the value of `array_on_stack` by default, simply type the following into "Watch Expressions" at the top to get the value: `array_on_stack` or `&(array_on_stack[0])`)  Plug these values into [this hexadecimal to decimal converter](http://www.binaryhexconverter.com/hex-to-decimal-converter).  What do these values represent?  What is the obvious difference between these two numbers (*Hint*: think magnitude)?  Why are they different?

Notice that we printed the memory addresses of the start of both arrays just like when we printed the value of `numberPtr` which was pointing to `number`.  This is because an array is accessed the same way that an integer is accessed when using a pointer.  In other words `array_on_stack` and `array_on_heap` *are* pointers.  The difference is that memory is reserved to store more than one element when instantiating an array. Also, when declaring a pointer meant to point to just one single integer we had to declare an integer separately and assign the pointer a memory address by using the `&` operator.

Let's prove to ourselves that `array_on_heap` is a pointer, and that its elements can be accessed using a different pointer.  In the code snippet below we set `numberPtr = array_on_heap`.  We should now be able to access the elements of `array_on_heap` using both pointers.

```C
// Make numberPtr point to array_on_heap
numberPtr = array_on_heap;
```

> **Question 7:** You should be paused at line `34`.  Step through the code once and inspect the values of `array_on_heap` and `numberPtr`.  What are the values and what do they represent?  Are they the same?

> **Question 8:** Now, in "Watch Expressions" type `array_on_heap[3]` and `numberPtr[3]`.  What are the values and what do they represent?  Are they the same?

**NOTE**: It doesn't matter if the array is on the heap or on the stack, the same principles apply.  We could set `numberPtr = array_on_stack` and achieved the same results (assuming we added elements to `array_on_stack` first).

## 5. Iterating through an array and accessing its elements.

```C
// Access the first element of the array
number = numberPtr[0];

// Dereference the first element of the array
number = *numberPtr
```

The above code accomplishes the same thing twice.  It sets `number` to the first element of our array by dereferencing the array pointer at its first position.  The syntax to dereference the array is `[]` in the case of the first example, and `*` in the case of the second.

> **Question 9:** Step through the code once, pausing at line `37`.  Inspect the value of `number`.  What is its value?  To get the memory address of `number` type `&number` in "Watch Expressions".  What is the address of `number`?  Step through the code once again, pausing at line `40`. Inspect the value of `number` again, what is its value?  Did the value of `number` change?  Why or why not?  Get the memory address of `number` again?  Did the value change?

Now that we know that an array pointer simply points to the first element in the array, let's examine how we traverse the array to access it elements.  Let's print out the memory address of the first two elements in `numberPtr`.  To do this we will simultaneously dereference the array element and get its memory address using the `&` operator as shown in the next question.

> **Question 10:** Enter the expressions `&numberPtr[0]` and `&numberPtr[1]` in "Watch Expressions".  You should get two different addresses.  What is the algebraic difference between the two values you just printed (use the hexadecimal to decimal converter if you need to).  Type `sizeof(int)` in "Watch Expressions".  Does the `sizeof(int)` method give you the difference between the memory addresses?

The algebraic difference from the previous question gives us the difference, in numbers of bytes, between two integers in memory.  Since an integer is 4 bytes (32 bits), the difference between integers in an array is represented by an increment of 4 in the memory address.

> **Question 11:** If the difference in memory addresses for an integer array is equal to `sizeof(int)`, what does this tell you about how a program knows where to find the next element in an array when starting from the first element (the element that the array pointer points to)?

> **Question 12:** How many bytes does a single memory address represent?  How many bits?

The next two lines of code are again, equivalent, except now we are getting the third element in our array.  The first line is self explanatory, using the `[]` syntax to dereference the array pointer.  The second example, however, uses pointer arithmetic to accomplish the same thing.  The syntax `numberPtr+2` tells the program to start at the first element of `numberPtr` and advance two more elements.  Step through these next two lines of code (you should pause at line `49`) and watch `number` each time to prove this to yourself.

```C
// Dereference the third element of the array
number = numberPtr[2];

// Dereference the third element of the array
number = *(numberPtr+2)
```

> **Question 13:** If `*numberPtr` gets the first element in the array, what element does `*(numberPtr+1)` return?  What about `*(numberPtr+5)`?  Using the `[]` syntax, what is the equivalent of `*(numberPtr+9)`?  Using the `[]` syntax, what is the equivalent of `*(numberPtr+7)`?  What is the algebraic difference between the memory addresses `numberPtr+2` and `numberPtr+5`?

> **Question 14:** What prints when you type `*(numberPtr+4) == numberPtr[4]` in "Watch Expressions".  Why?  What prints when you type `*(numberPtr+5) == numberPtr[5]` in "Watch Expressions".  Why?  What prints when you type `*(numberPtr+4) == numberPtr[5]` Why?

```C
// Advance numberPtr by three
numberPtr = numberPtr+3;

// Dereference numberPtr at its new location
number = *numberPtr;
```

So far we have seen how to dereference elements of `numberPtr` without changing the memory location that `numberPtr` points to.  It is possible, however, to update `numberPtr` using pointer arithmetic so that it points to a new memory address going forward.  The above code snippet advances the pointer by three elements.

> **Question 15:** What element number in `array_on_heap` does `numberPtr` point to now?  Using the `array_on_heap[]` syntax, what is the equivalent of `*numberPtr`?  Does `numberPtr[0] == array_on_heap[3]`?

**BEFORE PROCEEDING**: Let's get out of our debugging session so we can set a new breakpoint.  Either press the play button to let the program run to completion, or click on the terminal and press Control-C.  Next, delete all of your breakpoints by clicking on the red circles you created earlier.  Set a breakpoint at line `61`.

```C
// Make numberPtr point to array_on_stack
numberPtr = array_on_stack;

// Set number to 10
number = 10;

// Set each element of array_on_stack
for (int i = 0; i < number; i++)
{
	*numberPtr++ = i;
}
```

Now that we have seen that arithmetic operations can be applied to pointers, let's iterate through an array by incrementing the pointer one memory address at a time using the unary operator `++`.  In the above example `numberPtr = array_on_stack`, so now `numberPtr` can be used to access the elements in `array_on_stack` by setting these pointers equal to each other.  In the `for` loop, `numberPtr` is incremented by one for each pass of the loop.  However, the dereference operator `*`, and the assignment operator `=`, take precedence over the unary operator `++`.  This means that the current value of `numberPtr` gets dereferenced and updated before we increment the memory address.

> **Question 16:** Step through each iteration of the `for` loop beginning at line `63`.  Type `numberPtr` in "Watch Expressions" and inspect its value until the loop terminates and you are paused at line `67`.  Write down the value of `numberPtr` for each iteration.

> **Question 17:** When we increment `numberPtr` by one, what is the algebraic difference between the value of `numberPtr` before and after incrementing.  Why?

> **Question 18:**  Type `array_on_stack[5]` in "Watch Expressions".  What is this value?  Did the process of incrementing through `numberPtr` succeed in updating `array_on_stack`?

## 6. (Optional) Casting an `int *` as a `char *` to decode a secret message.

**BEFORE PROCEEDING** Ensure `secret-message.c` is in your current working directory.  Compile and run the program.  Take a look at the code, is it clear what is going on?

In this last code snippet we are doing something tricky.  We declare an integer array `secret_message` and assign each element in the array some number.  We then pass each element of this array to the function `printMessage()`.  The odd thing is that `printMessage()` expects a `char *` to be passed as an argument, not an `int` or an `int *`.  So how did we make this happen without the compiler complaining?  The trick is to cast the reference to each element in `secret_message` as a `char *` so that the function thinks the reference is pointing to a `char` and not an `int`.  The program doesn't know any better, all it knows is that we are passing some memory address, and that we told it that the memory address points to some character or string of characters.


```C
// The size of our array
int arraySize = 5;

// Declare the array
long secret_message[arraySize];

// The size of our number type
int typeSize = sizeof(long);

// Why choose these numbers?
secret_message[0] = 478560413032;
secret_message[1] = 431316168567;
secret_message[2] = 7827304;
secret_message[3] = 6648417;
secret_message[4] = 7696249;

// Call our method to print secret message
for (int i = 0; i < arraySize; i++)
{
	printMessage((char*)&secret_message[i],typeSize);
}

printf("\n");
```

> **Question 19:** In your own words describe how to create a secret message of your own.  What is the process to create an integer that encodes a word?  How many letters can an `int` hold?  How many letters can a `long` hold?
