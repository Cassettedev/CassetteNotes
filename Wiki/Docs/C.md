# The C programming language
[[Home]]
[[Cassette]]
[[Wiki]]
[[Blog]]

[[Humanities]]
[[STEM]]
[[Health]]
[[Docs]]

### Compiling
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
