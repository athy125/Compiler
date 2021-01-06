Compiler-Project
This repository contains the compiler designed in C following the language specifications provided in Language Specifications.pdf

The compiler parses input files according to the language specifications, and if the input is syntactically and semantically correct, it is capable of generating corresponding assembly-level code. Some testcases have been provided in Compiler/testcases.

As required for the project, the code is compatible for GCC version 5.4.0. and has been tested on Ubuntu 16.04 To run it on Windows, you will have to use cygwin.

To create the compiler
cd Compiler
make
This will create an executable file named compiler
To test the compiler on a testcase
Ensure you are in the directory containing the compiler executable
Run ./compiler <RELATIVE_PATH_TO_TESTCASE_FILE> <NAME_OF_ASM_FILE>
Choose among the 11 options to test the feature you want.
To create assembly-level code , choose option 10.
Choose option 0 to exit. (Ctrl + C would result with no output in the ASM file)
To run the asm file nasm -felf64 code.asm && gcc code.o && ./a.out (Using code.asm as the name of the asm file in this example)
Stages of compiling a testcase (Option 10)
Stage	Details
Lexical Analysis	Categorizes the contents of the input file as tokens (as per the language specifications).
Syntax Analysis	Creates a Parse Tree for the tokens being returned by the lexer. If an error is encountered in any of the above 2 stages, the compiler does not proceed to semantic analsysis.
Semantic Analysis	Creates an Abstract Syntax Tree for the coresponding Parse Tree and populates the Symbol Table. If an error is encountered during Semantic Analysis, the compiler does not proceed to code generation
Code generation	Generates corresponding assembly-level code. As per the project requirements, code generation is restricted to only those testcases which have a single function (main) and handle only integers.
