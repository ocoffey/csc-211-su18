# Assignment 00: Docker and CS50 (ungraded)

## 1. Docker

### 1.1 Installation

> **If you already have Docker installed, you may skip this step and go to step [2. Cleaning a Docker Installation](https://github.com/URI-CSC/csc-211-su18/blob/master/lab-00/readme.md#2-cleaning-a-docker-installation-optional-for-fresh-installs)**

#### Windows 10 Professional or Enterprise 64-bit

Follow the instructions provided here: [Docker Community Edition for Windows](https://store.docker.com/editions/community/docker-ce-desktop-windows)

#### Mac OS 10.10.3+

Follow the instructions provided here: [Docker Community Edition for Mac](https://store.docker.com/editions/community/docker-ce-desktop-mac)

#### Ubuntu

Follow the instructions provided here: [Docker Community Edition for Ubuntu](https://docs.docker.com/install/linux/docker-ce/ubuntu/) 

> Note, if you are on 18.04 you will need to make one change to the installation process. Under the "Install using the repository" section, step 4, instead of:

```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"
```

You **must** use:

```bash
sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   test"
```

This is only due to the fact that Docker's development cycle does not align to Ubuntu's release cycle. If you'd like more information, feel free to refer to: [Docker ticket for stable 18.04 release](https://github.com/docker/for-linux/issues/290)

#### Other Linux Distros

Select the appropriate distro from here, and follow all instructions: [Docker Community Edition Generic](https://www.docker.com/community-edition#/download)

#### Other Windows and Mac Users

If you are on Windows or Mac, and do not meet the requirements above, you **must** install the [Docker Toolbox](https://docs.docker.com/toolbox/overview/).

#### Side-note for Linux Users

If you are running linux, you don't actually need docker. You can run and compile everything in your terminal using shell commands and a text editor such as [vim](https://www.vim.org/) or [emacs](https://www.gnu.org/software/emacs/). If you would like to try something new and exciting, all instructors can help with bash commands and vim shortcuts.

HOWEVER, Docker allows for the use of the [CS50 IDE Offline](https://manual.cs50.net/ide/offline).  This is the default IDE for this class and instructors will be able to provide the best support to students who use this IDE.

Additionally, it is highly likely that you will use docker in the future. If you would like to install docker for linux, refer to the appropriate section above.

### 1.2 Documentation

Take a moment to look over the following resources, bookmarking them for later reference.

- [Windows 10 Docker documentation](https://docs.docker.com/docker-for-windows/)
- [Mac 10.10.3+ Docker documentation](https://docs.docker.com/docker-for-mac/)
- [Docker Tookbox documentation](https://docs.docker.com/toolbox/overview/)

If you'd like to have a useful cheat sheet, you may find one here:

- [Docker Information / Cheat Sheet](https://github.com/wsargent/docker-cheat-sheet#containers)

### 1.3 Verifying the Install

#### Windows

If you have the community edition of docker installed, open powershell (the command prompt would also work) and run `docker version`, then `docker run hello-world` to ensure everything installed properly.

> To open powershell, either click on the start button, or hit the Windows key, and type "powershell", then hit enter.

If you have the toolbox version of docker, launch the "Docker Quickstart" application from your start menu, or your desktop. Once you are presented with the `$` icon, type `docker run hello-world` and hit enter. If this command runs successfully, you have docker installed properly. 

#### Mac

If you have the community edition of Docker installed, open a terminal window and run `docker version`, then `docker run hello-world` to ensure everything installed properly.

> To open terminal, use finder to find the application called "terminal". 

If you have the toolbox version of Docker, launch the "Docker Quickstart" application from finder. Once you are presented with the `$` icon, type `docker version`, then `docker run hello-world` to ensure everything installed properly. 

#### Linux

To verify the installation on Linux, launch a terminal window, and enter `docker version`, then `docker run hello-world` to ensure everything installed properly. If you do not know how to open terminal on your version of linux, open whatever searching tool your distro comes with, and type in "terminal". If you do not know how to access your versions' search tool, please refer to your specific distros documentation (or Google it). There are simply too many distros in the wild to contain all relevant documentation here. 

## 2. Cleaning a Docker Installation (Optional for fresh installs)

This step will remove all existing containers and images. If you have just installed docker, this step is considered optional, moreover, if you have containers and/or images you are using for other classes **do not** complete this step. Generally, this step is targeted at those students who took this class last semester, we ask that you perform this step to ensure compatibility issues will not arise. 

If you would like to list all existing containers/images, use the commands `docker image ls` and `docker container ls`. 

You can then use `docker rmi [images]` and `docker rm [containers]` to remove each unused one individually.

If you want to wipe *everything* all in one go. Use these commands:

```bash
$ docker rm $(docker ps -a -q)
$ docker rmi $(docker images -q)
```

## 3. CS50 IDE

### 3.1 Installation

In this class we will be using the cs50ide, kindly provided [here](https://manual.cs50.net/ide/offline).

Please use the above link to install the IDE to your system.

> If you run the command provided and receive a `docker: Got permission denied ...` error, you **must** prepend `sudo ` to the command. As in: `sudo docker run --privileged -e "IP=127.0.0.1" -e "PORT=8080" --name ide50 -d -p 5050:5050 -p 8080-8082:8080-8082 cs50/ide`

### 3.2 Documentation

Feel free to look over, and bookmark, the documentation provided [here](https://manual.cs50.net/ide). 

### 3.3 Ensuring the cs50ide is running:

Click (or type if clicking doesn't work) the following in your browser to access the IDE:

> [http://localhost:5050](http://localhost:5050)

or

> [http://0.0.0.0:5050](http://0.0.0.0:5050])

If you installed the Docker Toolbox, the above links may not work. Instead type and enter the following line in the Docker QuickStart Terminal:

```bash
$ docker-machine ip default
```

And you will be given the ip address of your local Docker machine. 
In your browser type the ip address you received followed by the port :5050 to access the cs50ide.

For example, yours may look like:
> http://192.168.99.100:5050

### 3.4 Updating CD50 IDE:

1. At this point you may notice a banner along the top of your window noting that your current version is out of date, to update, run `update50` in the built-in shell, which should be titled 'workspace/'. You'll then have to restart the docker instance by running `docker restart ide50` in the **original terminal or powershell window** (this is the one one your desktop, not within the browser). Once you've restarted the IDE, refresh your browser to ensure you have all of the changes.

2. After restarting your computer, you will no longer be able to connect to the IDE using your browser. 
In order to access the IDE again, run the following command: (again, toolbox users will have to run this from the Docker Quickstart Application, Community Edition users can run this directly from terminal / powershell)

```bash
$ docker start ide50
```

## 4. Running a C program in the CS50 IDE

### 4.1 A New Interface

You should now be staring at your brand new IDE. Click on 'File', then select, "New File". Here is the basic anatomy of this screen featuring MSPaint.

![Screen shot of the IDE](https://github.com/URI-CSC/csc-211-su18/blob/master/assignments/a00/anatomy.png "Cloud9 IDE Annotated")

Once you have your new file, you may start typing and wonder why there is no Syntax Highlighting. The way fix this is to save your file as a '.c' file. Save your new file now as, 'hello.c'. 

### 4.2 Hello World

Now we will write our first program in the editor. Feel free to modify the code below to display whatever message you'd like. 

```c
#include <stdio.h>

int main(void)
{	
	printf("Hello World!\n");
	return 0;
}
```

### 4.3 Running programs

**You MUST save your work before compiling and running your code** CS50 IDE will try to warn you when you haven't with a large red banner across the top of your browser, but please be vigilant.  

### 4.4 Compiling your code using the bash terminal

Time to put the bash terminal to use. If you have never used shell, or bash before, do not worry. The first thing we should do is find the files we have available to us. Type this into the terminal. 

> The line should start with, `~/workspace/ $ `

```bash
$ ls
```

You should see, `hello.c`.

Now, it is to compile your program. We will use `gcc`. Simply type this below:

```bash
$ gcc hello.c -g -o hello
``` 

`-g` tells the compiler to include debugging symbols which allow you to use breakpoints to debug your code

`-o` tells the compiler that the next argument should be the name of the output file `hello` in this example

If you have any syntax errors they will be printed to you now. Assuming your program successfully compiled, you now have a machine code file called `hello`. You can see this new file by typing `ls` in the bash shell again, or looking in the file browser in the left hand panel in the browser.

Finally you must run your executable code by typing,

```bash
$ ./hello
``` 

Voila, you have just run, "Hello World!"

### 4.5 Shell Hints

Before we move on, there are a few things about the shell you should know. The up arrow goes to previous commands. And if you think the computer can guess what you are typing, you can hit TAB to have it completed for you. For example, if `gcc hel` is typed in terminal, and the TAB key is hit, the rest of the file name will be filed in.

## 5. Step-by-Step Debugging

Now you will running your program in debug mode; this mode allows you to run code line by line, or chunk by chunk, depending on where your breakpoints are. While the code is running, you can update variables and function calls, thus allowing you to find errors in your code more easily.

### 5.1 Setting a Breakpoint

Before you start debugging you must set a breakpoint in your code. In debug mode, your program will run normally until it reaches the breakpoint. You are now in control of when your program executes its lines of code. To set a breakpoint, click  on the light gray space in your file window that is to the left of the numbers column, on the line that you wish to start debugging. A big red circle should appear after clicking once, with a C++ example shown below:
![image](https://github.com/URI-CSC/csc-211-su18/blob/master/assignments/a00/breakpoint.png "Setting a breakpoint")

### 5.2 Running in Debug Mode

Now that you've set a breakpoint, we must run the program in debug mode. You can do this by running the `debug50` command.  For our example the following will run your program in debugging mode:

```bash
$ debug50 hello
```
![Screen shot of the debug cmd](https://github.com/URI-CSC/csc-211-su18/blob/master/assignments/a00/debug50.png "Debug Command")

### 5.3 Debugging "Hello World"

You should notice that your program stops executing at the breakpoint, and the line with the breakpoint is highlighted yellow. When debugging, the highlighted line is the next line of code to be executed. To the right you should see the debugging window, as shown below.   

![image](https://github.com/URI-CSC/csc-211-su18/blob/master/assignments/a00/debugWindow.png)  

The top row of buttons allow you to navigate and execute your code. From Left to Right: The play button, or the 'Resume' button, will stop debugging and run your program normally until it reaches another breakpoint, end of program, or a runtime error. The 'Step Over' and 'Step Into' buttons will both execute the next line of code. They perform differently when the next line of code includes a function. The Step Over button will execute the function call completely and finish executing the current line. The Step Into button will instead move the debugger to that function's code and continue debugging there. The Step Out button can be pressed when you are inside a function call to finish the function call and return to the original line of code that called that function. The Deactivate All Breakpoints button does just that.  

### 5.4 Debugging Another Program

It may help to practice debugging another program. Debugging this program will also show how the debugger displays information on the program's variables. 

Set a breakpoint for the first line (`int a = 2;`), and use the 'Step Over' command to view the 'Local Variables' at every 'step' in the execution of this program.

```c
int main() {
    int a = 2;
    int b = 4;
    int c = a + b;
    return 0;
}
```

In the 'Local Variables' section, you can double click any value, and change it on the fly. Rerun your debugger and try this, and see how it impacts the variable `c`.
