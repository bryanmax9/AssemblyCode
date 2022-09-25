# AssemblyCode
Here I'll leave my assemblycode that I have done so far


An assembly program can be divided into three sections −

    *The data section,

    *The bss section, and

    *The text section.


The data Section

The data section is used for declaring initialized data or constants. This data does not change at runtime. You can declare various constant values, file names, or buffer size, etc., in this section.

The syntax for declaring data section is −

section.data

The bss Section

The bss section is used for declaring variables. The syntax for declaring bss section is −

section.bss

The text section

The text section is used for keeping the actual code. This section must begin with the declaration global _start, which tells the kernel where the program execution begins.

The syntax for declaring text section is −

section.text
   global _start
_start:


Comments

Assembly language comment begins with a semicolon (;). It may contain any printable character including blank. It can appear on a line by itself, like −

; This program displays a message on screen

or, on the same line along with an instruction, like −

add eax, ebx     ; adds ebx to eax


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

Syntax of Assembly Language Statements

Assembly language statements are entered one statement per line. Each statement follows the following format −

[label]   mnemonic   [operands]   [;comment]

The fields in the square brackets are optional. A basic instruction has two parts, the first one is the name of the instruction (or the mnemonic), which is to be executed, and the second are the operands or the parameters of the command.

Following are some examples of typical assembly language statements −

INC COUNT        ; Increment the memory variable COUNT

MOV TOTAL, 48    ; Transfer the value 48 in the 
                 ; memory variable TOTAL
					  
ADD AH, BH       ; Add the content of the 
                 ; BH register into the AH register
					  
AND MASK1, 128   ; Perform AND operation on the 
                 ; variable MASK1 and 128
					  
ADD MARKS, 10    ; Add 10 to the variable MARKS
MOV AL, 10       ; Transfer the value 10 to the AL register



Source were was gotten the information: https://www.tutorialspoint.com/assembly_programming/assembly_basic_syntax.htm
