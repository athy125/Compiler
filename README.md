# Compiler Project

This repository hosts a comprehensive compiler implemented in C, adhering to the language specifications outlined in the document named "Language Specifications.pdf."

The compiler efficiently analyzes input files based on the specified language rules, ensuring both syntactic and semantic correctness. It is capable of generating assembly-level code when the input passes the validation process. A set of test cases is provided in the "Compiler/testcases" directory.

To ensure compatibility, the code has been developed and tested with GCC version 5.4.0 on Ubuntu 16.04. If you intend to run the compiler on Windows, the usage of Cygwin is recommended.

To build the compiler, follow these steps:
1. Navigate to the "Compiler" directory.
2. Execute the "make" command.
3. This will create an executable file named "compiler."

To test the compiler using a specific test case, perform the following:
1. Ensure you are in the directory containing the compiler executable.
2. Run the command: `./compiler <RELATIVE_PATH_TO_TESTCASE_FILE> <NAME_OF_ASM_FILE>`
3. Select one of the provided 11 options to test the desired feature.
4. Option 10 generates assembly-level code.
5. Use option 0 to exit (Ctrl + C will result in no output in the ASM file).

To run the generated assembly-level code, follow these steps:
1. Execute: `nasm -felf64 code.asm && gcc code.o && ./a.out` (Replace "code.asm" with the actual name of the assembly file in use).

Compilation stages for a given test case (Option 10):
Stage       | Details
------------|----------------------
Lexical Analysis   | Identifies and categorizes the content of the input file as tokens, following the language specifications.
Syntax Analysis    | Constructs a Parse Tree for the tokens provided by the lexer. If any error occurs during the previous two stages, the compiler halts and does not proceed to semantic analysis.
Semantic Analysis  | Builds an Abstract Syntax Tree based on the generated Parse Tree and populates the Symbol Table. If any error arises during Semantic Analysis, the compiler does not proceed to code generation.
Code Generation     | Produces assembly-level code corresponding to the input program. Notably, the code generation is limited to test cases that include a single function (main) and handle only integers.

