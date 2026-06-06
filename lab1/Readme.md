# LAB 1: Deconstructing the C Compilation Pipeline

## Objective
The objective of this lab is to systematically analyze how a C program is transformed into an executable by isolating and examining each stage of the GCC toolchain, including preprocessing, compilation, assembly, and linking, along with understanding the internal transformations that occur at each stage.

---

## Theory
A C program does not directly become an executable file. Instead, it passes through four distinct stages, where each stage progressively converts the program into a lower-level representation.

The first stage is **Preprocessing**, which is handled by the preprocessor (cpp). In this stage, directives such as `#include` and `#define` are processed. Header files are expanded, macros are replaced with their actual values, and comments are removed. The output of this stage is an expanded source code file with a `.i` extension. For example, when compiling with the command `gcc -E lab1.c -o lab1.i`, the `<stdio.h>` header expands into a large amount of code, and macros are substituted directly into the source file. This demonstrates that C preprocessing is mainly a text substitution phase.

The second stage is **Compilation**, where the preprocessed code is converted into assembly language. During this stage, syntax and semantic analysis are performed, and optimizations may also be applied. The output of this stage is an assembly file with a `.s` extension. Using the command `gcc -S lab1.c -o lab1.s`, the high-level C code is translated into assembly instructions. At this stage, variables are mapped to CPU registers and function calls such as `printf` become visible, showing the transition from high-level logic to low-level machine representation.

The third stage is **Assembly**, where the assembly code is converted into machine code by the assembler (as). This produces an object file with a `.o` extension. When the command `gcc -c lab1.c -o lab1.o` is executed, the output file becomes binary and unreadable in a text editor. However, tools like `nm lab1.o` can be used to inspect symbols. At this stage, the object file contains machine code but is still incomplete because external references, such as library functions, are not yet resolved.

The final stage is **Linking**, where the linker combines object files with required libraries and resolves external references. The final output is an executable file. Using the command `gcc lab1.o -o lab1`, the program is linked with system libraries. When executed using `./lab1`, the program runs successfully. Without this stage, functions like `printf` would not work because their definitions are not included in the object file.

---

## Conclusion
The execution of a C program involves four major stages: preprocessing, compilation, assembly, and linking. Each stage transforms the program into a more machine-level representation. Understanding this pipeline is essential for debugging, optimization, and gaining a deeper understanding of how programs are executed at the system level.
