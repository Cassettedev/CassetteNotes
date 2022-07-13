# x86_64 Assembly Language on Linux
Assembly language is human-readable machine code

To compile assembly on linux, I use NASM.

You first create an assembly file ending in `.asm`
```
touch hello.asm
```

To compile it, you use NASM like so:
```
nasm -f elf64 -o hello.o hello.asm
```
`elf64` refers to the file format linux uses for `.asm` files. `-o` means output, `hello.o` is the file we want to make and `hello.asm` is the file we want to compile. This will create a `hello.o` file.

Once you have a `.o` file, you need to link it to make it an executable file. You can use `ld`, the GNU linker, like so:
```
ld hello.o -o hello
```
`hello.o` refers to the object file we created, `-o` still means output, and `hello` is the name of the executable file we want to make.

To execute the file, type:
```
./hello
```

## Making a Hello World Assembly program
The program we are going to make is:
```
section .data
		text db "Hello, World!",10

section .text
		global _start

-start:
		mov rax, 1
		mov rdi, 1
		mov rsi, text
		mov rdx, 14
		syscall
		
		mov rax, 60
		mov rdi, 0
		syscall
```

### db
`text db "Hello, World!,10"`
`db` means 'define bytes' meaning it defines some amount of raw bytes of data to insert into our code.

`"Hello, World!",10`
This is the bytes of data that is being defined. Each character is a single byte, including the space and the `10`.

`text`
This is the name of the address in memory that this data is assigned to. `text` can be used later in the code to refer to this location in memory. When the code is compiled, the compiler will find the actual location in memory and replace all instances of `text` with that memory address.

This whole process can be thought of as defining a variable.

### Registers
Registers are the part of the processor that temporarily holds memory. In x_86_64 architecture, each register holds 64 bits. Therefore, each register can hold the values:
```
Unsigned: 0 	                    -18,446,744,073,709,551,616

Signed: -9,223,372,036,854,775,808  -9,223,372,036,854,775,807 
```

The registers for 8-bit, 16-bit, 32-bit, and 64-bit machines respectivly are:

| 8-bit | 16-bit | 32-bit | 64-bit |
| ----- | ------ | ------ | ------ |
| al | ax | eax | rax |
| bl | bx | ebx | rbx |
| cl | cx | ecx | rcx |
| dl | dx | edx | rdx |
| sil | si | esi | rsi |
| dil | di | edi | edi |
| bpl | bp | ebp | rbp |
| spl | sp | esp | rsp |
| r8b | r8w | r8d | r8 |
| r9b | r9w | r9d | r9 |
| r10b | r10w | r10d | r10 |
| r11b | r11w | r11d | r11 |
| r12b | r12w | r12d | r12 |
| r13b | r13w | r13d | r13 |
| r14b | r14w | r14d | r14 |
| r15b | r15w | r15d | r15 |

As you can guess, the amount of 'bits' a register has depends on the machine. An 8-bit machine as registers with 8 bits, 16-bit with 16, etc. You can use lower bit registers within a larger machine. Eg, using 8-bit registers in a 32-bit machine.

### Syscall
A system call, `syscall`, is when a program requests a service from the kernal of the OS. Because of this, different operating systems have different syscalls.

All syscalls have an ID associated with them. They also take 'arguments', a list of inputs.

#### System Call Inputs by Register
| Argument | Register |
| ---------- | --------- |
| ID | rax |
| 1 | rdi |
| 2 | rsi |
| 3 | rdx |
| 4 | r10 |
| 5 | r8 |
| 6 | r9 |

If you want to call a `syscall`, you first have to load the ID of the `syscall` into the `rax` register and then load your arguments into registers 1-6, and then call `syscall`. 

#### System Call List
| syscall | ID | Argument 1 | Argument 2 | Argument 3 |
| ------- | -- | ---------- | ---------- | ---------- |
| sys_read | 0 | filedescriptor | buffer | count |
| sys_write | 1 | filedescriptor | buffer | count |
| sys_open | 2 | filename | flags | mode |
| sys_close | 3 | filedescriptor | | |
| ... | ... | ... | ... | ... |
| pwritev2 | 328 | ... | ... | ... |
There may be more syscalls

#### sys_write
| Argument Type | Argument Description |
| ---------------- | ---------------------- |
| File Descriptor | 0(standard input), 1(standard output), 2(standard error) |
| Buffer | Location of string to write |
| Count | Length of string |

When we do:
```
mov rax, 1
mov rdi, 1
mov rsi, text
mov rdx, 14
syscall
```
We are moving the `sys_write` argument ID, 1 in this case, into `rax` because that is the register that takes the syscall ID. We then move `1`, the argument for standard output, into the `rdi` register as argument 1. We then move the location, the memory address, of our `text` into the `rsi` register as argument 2.  We then move the length of our string into the `rdx` register as the next argument 3.

`mov` means to move data around.

![[ASM_registers.png]]

When we do:
```
mov rax, 60
mov rdi, 0
syscall
```
We are moving the `sys_exit` argument ID, 60, into `rax` because that is the register that takes the syscall ID. We then move `0` into the `rdi` register as an argument that defines an error, an error code. If the error code is `0`, it means there is no error.

![[ASM_sys_exit.png]]

#### In python and other code
To write this code in pseudocode, it would look something like:
```
text = "Hello, World!"

sys_write(1,text,14)
sys_exit(0)
```
Where `1` is the argument descriptor, `text` is the "variable name" (name of the adress store in memory containing thr data), and `14` is the length of the string. We do not need to put `1` and `60` into the function arguments because they refer to the '`syscall`', the 'function', itself.

You could alsowrite it as:
```
1(1,text,14)
60(0)
```
If you wanted to replace `sys_write` and `sys_exit` with their argument IDs.

If we were to write the same code in something like python, it could look something like:
``` python
text = "Hello, World!"

print(text)
```
Although, there are many ways to interpret the code.

### Sections
All x86_64 assembly files have three sections;
```
section .data

section .bss

section .text
```

`section . data` is where all the data is defined before compilation. `section .bss` is where you allocate memory for future use. `section .text` is where the "actual code" goes.

### Labels
A Label *lables* a section of the code. Once the code is compiled, the compiler will allocate a location for the label to sit in memory. Any time the name of the label is used afterwards, the compiler will find the location of the label, the section of code, in memory. It functions much like `text db "Hello, World!",10`.

#### Start label
The `_start` label is essential. When the program is compiled and executed, it is first executed at the location of `_start`. The linker will throw an error otherwise.

#### Global
`global` is used when you want the linker to know the address of a label. The object file, `.o`, will have a link to every label declared `global`. Declaring `_start` as `global` is essential for the code to be linked properly.