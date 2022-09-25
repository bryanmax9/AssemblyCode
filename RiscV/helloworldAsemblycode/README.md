The Hello World Program in Assembly

The following assembly language code displays the string 'Hello World' on the screen −

<pre class="prettyprint notranslate prettyprinted" style=""><span class="pln">section	</span><span class="pun">.</span><span class="pln">text
   </span><span class="kwd">global</span><span class="pln"> _start     </span><span class="pun">;</span><span class="pln">must be declared </span><span class="kwd">for</span><span class="pln"> linker </span><span class="pun">(</span><span class="pln">ld</span><span class="pun">)</span><span class="pln">
	
_start</span><span class="pun">:</span><span class="pln">	            </span><span class="pun">;</span><span class="pln">tells linker entry point
   mov	edx</span><span class="pun">,</span><span class="pln">len     </span><span class="pun">;</span><span class="pln">message length
   mov	ecx</span><span class="pun">,</span><span class="pln">msg     </span><span class="pun">;</span><span class="pln">message to write
   mov	ebx</span><span class="pun">,</span><span class="lit">1</span><span class="pln">       </span><span class="pun">;</span><span class="pln">file descriptor </span><span class="pun">(</span><span class="pln">stdout</span><span class="pun">)</span><span class="pln">
   mov	eax</span><span class="pun">,</span><span class="lit">4</span><span class="pln">       </span><span class="pun">;</span><span class="pln">system call number </span><span class="pun">(</span><span class="pln">sys_write</span><span class="pun">)</span><span class="pln">
   </span><span class="kwd">int</span><span class="pln">	</span><span class="lit">0x80</span><span class="pln">        </span><span class="pun">;</span><span class="pln">call kernel
	
   mov	eax</span><span class="pun">,</span><span class="lit">1</span><span class="pln">       </span><span class="pun">;</span><span class="pln">system call number </span><span class="pun">(</span><span class="pln">sys_exit</span><span class="pun">)</span><span class="pln">
   </span><span class="kwd">int</span><span class="pln">	</span><span class="lit">0x80</span><span class="pln">        </span><span class="pun">;</span><span class="pln">call kernel

section	</span><span class="pun">.</span><span class="pln">data
msg db </span><span class="str">'Hello, world!'</span><span class="pun">,</span><span class="pln"> </span><span class="lit">0xa</span><span class="pln">  </span><span class="pun">;</span><span class="kwd">string</span><span class="pln"> to be printed
len equ $ </span><span class="pun">-</span><span class="pln"> msg     </span><span class="pun">;</span><span class="pln">length </span><span class="kwd">of</span><span class="pln"> the </span><span class="kwd">string</span></pre>

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
