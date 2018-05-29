# Mastering Bash

This assignment is focused on your fluency with Bash, it should be completed in the CS50 IDE, and will require that you create and run bash scripts. It will also include some questions on fundamental types in C, and walk you through how to clone this courses Github Repository into your workspace (which will make life much easier throughout the semester).

## Bash

Start by opening up CS50 IDE. 

> You may need to restart the IDE itself, to do so, with the Community Edition, open terminal and run `docker start ide50`. If you are using the Toolbox, open your Docker Quickstart environment, and run the command `docker start ide50`. 

### 0) Hello World

Create a new file, called `hello.sh`. 

> This suffix `.sh` signifies that this file will contain a shell script. 

Open the file and write the line: `echo "Hello World!"`

Save the file, and navigate to the terminal in the IDE. Run the command `source hello.sh`. Using source here allows you to run shell scripts without changing permissions of the file. 

You should now see "Hello World!" has been printed to your terminal window, congratulations! You've just written your first Bash Script!

### 1) Creating Projects

Bash scripts operate just like your terminal, except you get to write all the commands down before you execute, rather than having to type them in one at a time when prompted. For this problem you must recreate all the steps below in a stand-alone script. 

We're going to build a fake project together, called "Hello universe!". 

> Note that all of the following should be run in the terminal prompt, do this before starting to write the script.

1) Making the directory: run `mkdir hello_universe`. Note that the new folder is already present in your file tree.

2) Changing to be in that directory: run `cd hello_universe`.

3) Print existing files within that directory: `ls` There should be nothing present *yet*.

4) Create a new file: `touch main.c`. Touch creates a file if one does not exist, and does nothing if it does. It is a very safe way to create new files from terminal.

5) Create another new file: `touch compile.sh`

6) Now, let's write a bare-bones compile script: `echo "gcc *.c -o hello.o" >> compile.sh`. There's quite a bit to unpack in this small statement; however, at the highest level, what we are executing here says 'print the line "gcc *.c -o hello.o" to the file named compile. The `>>` symbol is a *redirection*, that takes the output of whatever command is on it's left, and 'pipes' it to whatever is on it's right. This principle allows long chains of commands to pass information, allowing you to be a much more powerful Bash developer. 

> At this point, feel free to re-run the command above, redirecting the output to different files, such as `compile.txt`, etc. Note the default behavior when a file does not already exist.

You now have a new directory, with a generic compile script and a blank `.c` file to work with! If you run `source compile.sh` now, you will see an `undefined reference to 'main'` error, you **do not** have to fix this error, but rather think about what the compiler is telling you. Reading error codes will become an invaluable skill as this class progresses. 

At this point, you can repeat all the steps above (for better understanding), or you can dive right in and create a shell script to perform all of the above actions. Save this script as `create_hello_universe.sh`.

### 2) Cleaning up Directories

At this point, you should still be within the `hello_universe` directory. You can always check your current directory by either looking to the left of the `$` character in your terminal, **or** by running `pwd` which will print the full "present working directory" to the terminal.

We will now clean up our project, since we no longer need the folder.

1) Start by navigating back up the folder structure one level: `cd ..`. Also run `cd .` and think about what happens.

2) List the files in the new current directory: `ls`

3) Once you're sure that `hello_universe/` is present, try running `rm hello_universe/`. In order to remove a directory, you must tell the remove command to run *recursively*. We will cover recursion in much greater detail later in the semester, for now, adding a "flag" `-r` will do the trick. Flags are normally added after the command, yet before the target, in this case: `rm -r hello_universe/` will do the trick.

> Note that this combination of flags will cause bash to prompt you for each item you wish to remove. To skip this step and remove everything, you can add another flag: `-f`. Adding flags takes two distinct forms in Bash, you can either write `rm -rf <target>`, or you may write `rm -r -f <target>`. Either will do just fine.

**Warning** Remove doesn't have a trash can. When you remove something, it not only *unlinks* the data, it also clears any metadata that could be used to restore it. Be sure you want to remove something before you run the `rm` command. Or, use git, which allows you to revert any changes, even removing files.

### 3) Finding Help

If you ever have trouble with a bash command, the Unix system is there to help! 

Run `man ls` in your terminal window, and examine the output. 

Running man is a great way to familiarize yourself with bash commands, note that most options won't be needed for many of the commands.

### 4) Going Further with Github

**This is an optional section**

Github is a version-control system capable of saving you countless hours of development time. It allows users to save all of their code to the Github servers, create branches in your code to examine other potential solutions, and much more. Particularly, in this class, it can be very helpful to have the csc211 repository directly inside of the IDE. To do this, navigate back to the `workspace` directory, and run `git clone https://github.com/URI-CSC/csc-211-su18.git`. 

Now that you have the repo in your workspace, there are many new things you can do! To start with, you can now preview assignments directly in your editor! To do so, navigate to any `.md` file, and right-click; from the menu, select "Preview". It's all well and good to have the rendered assignment in your workspace, but what if you want to write code while looking at the assignment? Simply right-click on the tab with the Markdown Preview, and select "Split pane in two columns" to 'push' the Markdown over to the right hand side of the editor. 

To stay in sync with the class as the semester progresses, you can simply run `git pull` to refresh your copy, with the one that the instructors post to. Note that `git pull` only works when inside of a Github repository, **before** you run the command, be sure to `cd` into the `csc-211-su18` directory. 

### 5) Going Further with Vim

**This is an optional section**

If you enjoy bash, and the terminal in general, you are not alone! There is much more you can do with terminal, in fact, you can turn terminal into a full-blown editor! Vim is a software package that provides a helpful editor anywhere you can use terminal. To learn how to use Vim, you can run `vimtutor` from the CS50 IDE terminal. Completing this tutorial a few times will help you master one of the most powerful terminal-tools out there! Once you've mastered the `vimtutor`, there are many more online resources for learning the advanced features of the editor.

## Primitive Types

Please complete the table below:

data type | min value | max value 
----------|-----------|-----------
char | | 
unsigned short | |
signed short | |
unsigned int | | 
signed int | | 
unsigned long | |
signed long | |
unsigned long long | |
signed long long | |
