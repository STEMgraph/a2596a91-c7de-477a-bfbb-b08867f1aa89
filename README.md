<!---
{
  "id": "a2596a91-c7de-477a-bfbb-b08867f1aa89",
  "teaches": "printf for constant Strings",
  "depends_on": [],
  "author": "Stephan Bökelmann",
  "first_used": "2025-03-20",
  "keywords": ["learning", "exercises", "education", "practice", "C", "printf"]
}
--->

# printf for constant Strings

## 1) Introduction
`printf` is a C function, that gives us access to the ability to write a **string** to the **standard output** (stdout) of the environment in which our program is executed.
The stdout usually being the terminal from which the program was launched.

The `printf` function is part of C's standard library.
It's definition is located in the `stdio.h` file. 
This stands for `Standard Input and Output`.
Looking at the language manual for C, gives us some information on how this function can be used. 
Let's look at one of many ways to use it:
```C
int printf( const char* restrict format, ... );
```
This look might scare a beginner in the first moment, so let's unpack it a little bit.
First, let's talk about the return-type. 
In a language reference, the return-type is usually written in front of the functions synopsis, in this case: `int`.
A way to think about this is that, when the computer is done evaluating the function, it promises to return an integer. 
Another way could be that, when the function has run, the value of `printf( ..... )` becomes an `int`.
In the parenthesis, the parameters that the function call awaits are displayed. 
The function `printf` seems to take two parameters, separated by a comma. 
The first one being called `format` with additional type-information in front of it. 
While the second one is `...`. 
This `...` is also called an __ellispis__ and can be a placeholder for an undefined number of arguments, also called a __variadic amount__ in programming. 
That undefined number may also be zero, so let's go with that for a moment, leaving us only with the first parameter.
Reading a little bit further in the documentation gives us the following information about the `format` variable-identifier:
```
format - pointer to a null-terminated byte string specifying how to interpret the data
```
If you haven't heard about pointers yet, don't worry. 
You can imagine them as an address-number within your RAM (from here on forth just **address**), where the first character of a multi character word or sentence is stored.
The next higher address is the next character. 
An ending of a word, sentence or just series of characters is indicated by a byte in RAM, which is completely set to zero (in binary: 0b 0000 0000).
A sequence of characters that fulfil this pattern is also called a __C-style-string__(-of-characters) or short: **String**.

There are a couple of other `printf` like functions in the `stdio.h` library. 
They will get interesting later.

### 1.1) Further Readings and Other Sources
- [printf on cppreference.com](https://en.cppreference.com/w/c/io/fprintf)

## 2) Tasks
1. **Write a simple program with printf**: To use `printf` you will have to first include the library and then call the function. This might look something like this:
```C
#include<stdio.h>

int main(){
    printf("Hello World");
    return 0;
}
```
Write this into a plain textfile and save it to your hard-drive. 
It's filename should end in `.c` - e.g. `my_new_program.c`.
This file is also called `source-code`.
Make sure, to set the semicolons correctly, otherwise your program will not work as intended.
2. **Installing the compiler**: In order for the program to be executable by our platform (computer), it needs to be translated into a format, that the platform can read.
This is done by the compiler. 
Try running `gcc --version` from your terminal. 
`gcc` is one of the most commonly used compilers today. 
If `gcc` isn't already installed, google for the installation-instructions for your platform - Windows, Linux, or MacOS.
3. **Run the compiler**: The installed compiler is a program as every other program as well. In order to run it, you need to type its name into the command-line on your terminal and pass it the path to the data it shall work with. In our case that is `my_new_program.c`. 
Assuming you are in the same directory where your source-code is located, you can now run the compiler by typing:
```shell
gcc my_new_program.c
```
If your file is located in a different directory, you can either choose to navigate into the directory using the `cd` command, or just use the fully-qualified-path, or __absolute path__:
```shell
gcc /home/user/directory/where/my/source/is/located/my_new_program.c
```
If the compiler doesn't give you any messages, your compilation ran smoothly and nothing went wrong. 
If something is wrong with your source-code or your installation, the compiler will issue `diagnostic-messages` to the terminal. 
Read them carefully and try to understand them. 
The compiler is your friend and just wants to help you with these messages. 
After reading them carefully, make sure, that your source-file looks as described in task 1.
4. **Searching the final program**: Assuming the compiler didn't issue any diagnostics, your ready to run program is now located in the exact directory you ran `gcc` from.
Use the `ls` command if you are working on a Mac or Linux shell, or `dir` if you are working on a DOS/Windows shell.
A new file should have been created called `a.out`. 
This is your executable program.
5. **Modifying the programs name**: `a.out` isn't really a good name for an executable. Therefore `gcc` gives us the opportunity to rename our final program easily.
Run `gcc` again, now in the following way:
```shell
gcc <path to your program.c> -o Executable_Program
```
The additional parameter is indicated by `-o`. 
This is the path, that our executable file will be stored at. 
Run `ls` or `dir` again, to see the file.
6. **Running the program**: In order to execute the program, type:
```shell
./Executable_Program
```
If you are running a linux or mac shell, or:
```dos
.\Executable_Program.exe
```
If you are running a windows/DOS shell.
Your output shall be printed to the terminal.

## 3) Questions

1. What does `printf` do, and why is it useful in a C program?
2. Why do we need to include `stdio.h` when using `printf`?
3. What is the difference between `printf("Hello World")` and `printf("Hello World\n")`?
4. How can you change the output filename when compiling a C program using `gcc`?

## 4) Advice

Make sure to always check for compiler diagnostic messages when writing C programs. They often contain useful hints. Additionally, experiment with modifying the `printf` statement—try adding `\n` or `\t` to your string and see what happens. Hands-on practice will solidify your understanding!


