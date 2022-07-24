# TODO
Pointers maybe???????
User input
Arrays
2d Arrays
Functions
If
Switch
While
For
Structs

# The C Programming Language
The C Programming Language is hard. It requires you to handle your own memory, and it comes with few features built in

## Header files
Header files are files that are included at the start of a program. They act as an API of sorts, allowing the programmer to have more functionality, such as handling input and output.
```C
#include <stdio.h>
```

## Main()
All code is held inside the main function
```C
int main()
{
	your code goes here
}
```

## Data types and variables
- char: a single 8-bit characer.
```C
char grade = 'A';
```
- char variable[]: the square brackets make it an array. This functions as a string of characters
```C
char name[] = "Greg";
```
- short: a 16-bit singed integer. -32,768 to 32,676 in value if singed
```C
short age0 = 10;
```
- int: a 16-bit integer, always bigger than `short`. at most -2,147,483,648 to 2,147,483,647 in value if signed
```C
int age1 = 20;
```
- long: a 32-bit integer. at most -9,223,372,036,854,775,808 to 9,223,372,036,854,775,807 in value if signed
```C
long age2 = 30;
```
- float: a 32-bit integer that goes to a precice range of 6 decimal places. 1.2E-38 to 3.4E+38 value
```C
float gpa0 = 2.5;
```
- double: a 46-bit integer that goes to a pecise range of 15 decimal places. 2.3E-308 to 1.7E+308 value
```C
double gpa1 = 3.4;
```
- long double: an 80-bit integer that goes to a precise range of 19 decimal places. 3.4E-4932 to 1.1E+4932 value
```C
long double gpa2 = 3.5;
```

Variables can be created and assigned later in the code.
```C
int age;
age = 34;
```

Constants can be made with:
```C
const int AGE = 34;
```
making the variable all caps is not required, only convention.

Variables can be printed in `printf()` by subsituting the variable with these:
- `%c` character
- `%d` integer number
- `%e` eponential floating point number
- `%f` floating point number
- `%i` integer
- `%o` octal number
- `%s` a string of characters
- `%u` unsigned decimal (integer) number
- `%x` number in hexadecimal
- `%%` print a percent sign
- `\%` print a percent sign

for example:
```C
printf("%s, your grade is %c \n", name, testGrade);
```

## Casting
Casting is converting a datatype of one variable to another. For example:
```C
printf("%d \n", (int)3.14);
printf("%f \n", (double)3 / 2);
```

## Pointers
A pointer is just a variable that holds a memory adress. Here is a table that acts as an example:

| address  | value |
| -------- | ----- |
| 100 |    |
| 101 |    |
| 102 |    |
| 103 |    | 
| 104 |    |
| 105 |    |
| 106 |    |

In our program, we have a variable `int a = 5;`. When we compile the program, the compiler assigns the variable name "a" to address `102`, and the value `5`. Whats really going on is the compiler goes to *somewhere* in RAM, address `102` in this case, and assigns the value of `5` into it. For all intents and purposes, the variable name `a` disapears to the computer.

| address  | value |
| -------- | ----- |
| 100 |    |
| 101 |    |
| 102 : a | 5  |
| 103 |    | 
| 104 |    |
| 105 |    |
| 106 |    |

Let's say we then make a variable `pointer b;`. When compiled, the variable is stored at a random address like any other variable, address `104` in this case. You could *theoretically* set the memory address it's pointing to manually, `pointer b = 102;` for example, but this is impractical. It's easier to use the location of the variable we want to point to as the value we give to the pointer. In C and C++ we use the `&` symbol, which can be thought of as `get the address of`. We can do `pointer b = &a;`, which now points to the address of wherever `a` is stored in memory. 

| address     | value |
| ----------- | ----- |
| 100 |       |
| 101 |       |
| 102 : a | 5     |
| 103 |       | 
| 104 : b|  102   |
| 105 |       |
| 106 |       |

Now that we have these two variables, we can make a third variable that has the value of *the location* pointed to by `b`. In C and C++, this looks like, `int c = *b;`. `*` Is not multiplication, it can be thought of as `get the value at`. The variable `c` will be stored somewhere in memory like any other variable, `101` in this case, and stores the value `5`, the same value that is held at `104`, which is what `b` is pointing to.

| address   | value |
| --------- | ----- |
| 100 : c | 5   |
| 101 |     |
| 102 : a | 5   |
| 103 |     | 
| 104 : b | 102 |
| 105 |     |
| 106 |     |

## Compiling
To compile a C program using GCC, use:
`gcc file.c -o filename`
And then to execute:
`./filename`

With a basic Hello World as an example, titled main.c:
```C
#include <stdio.h>

int main(){
	printf("Hello World\n");
	return 0;
}
```
Compile:
`gcc main.c -o hello`
Execute:
`./hello`
Output:
`Hello World`
