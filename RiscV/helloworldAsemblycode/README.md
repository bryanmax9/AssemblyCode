The Hello World Program in Assembly

The following assembly language code displays the string 'Hello World' on the screen −

ection	.text
   global _start     ;must be declared for linker (ld)
	
_start:	            ;tells linker entry point
   mov	edx,len     ;message length
   mov	ecx,msg     ;message to write
   mov	ebx,1       ;file descriptor (stdout)
   mov	eax,4       ;system call number (sys_write)
   int	0x80        ;call kernel
	
   mov	eax,1       ;system call number (sys_exit)
   int	0x80        ;call kernel

section	.data
msg db 'Hello, world!', 0xa  ;string to be printed
len equ $ - msg     ;length of the string

When the above code is compiled and executed, it produces the following result −

Hello, world!

////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Compiling and Linking an Assembly Program in NASM

Make sure you have set the path of nasm and ld binaries in your PATH environment variable. Now, take the following steps for compiling and linking the above program −

    *Type the above code using a text editor and save it as hello.asm.

    *Make sure that you are in the same directory as where you saved hello.asm.

    *To assemble the program, type nasm -f elf hello.asm

    *If there is any error, you will be prompted about that at this stage. Otherwise, an object file of your program named hello.o will be created.

    *To link the object file and create an executable file named hello, type ld -m elf_i386 -s -o hello hello.o

    *Execute the program by typing ./hello

If you have done everything correctly, it will display 'Hello, world!' on the screen.
