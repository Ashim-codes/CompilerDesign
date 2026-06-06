# LAB 3: Token Counter for Identifiers, Keywords & Operators Using Flex

## Experiment Title
Token Counter for Identifiers, Keywords & Operators using Flex

---

## Aim
The aim of this experiment is to develop a lexical analyzer using Flex that scans input code and identifies tokens such as keywords, identifiers, numbers, operators, and comments, while also counting how many times each token type appears in the input.

---

## Software Requirements
Flex is used as a lexical analyzer generator, and GCC is used as the C compiler to compile the generated code. The experiment is performed on a Windows operating system using MinGW as the development environment.

---

## Theory
The main purpose of a lexical analyzer is not only to identify tokens in a program but also to analyze their frequency, which is useful in later compiler stages such as optimization and symbol table generation.

In this experiment, regular expressions are used to define different token types such as keywords, identifiers, numbers, operators, and comments. Each time a token is matched, Flex actions written inside `{ ... }` are used to increment counters and print the token in real time. This helps in both recognizing and tracking the occurrence of each token type in the input program.

---

## Compilation and Execution Steps
The program is compiled and executed using the following commands:

```bash id="lab3cmd"
flex token_counter.l
gcc lex.yy.c -o token_counter
./token_counter
```




## Result
The Flex program successfully identified all tokens from the input source code and correctly counted the occurrences of each token type. It was able to distinguish between keywords, identifiers, operators, numbers, and other symbols while providing a detailed summary of token frequency.

---

## Conclusion
This experiment helped in understanding the practical implementation of lexical analysis using Flex. It demonstrated how regular expressions are used to recognize tokens and how Flex actions are used to maintain counters for different token types. The experiment improved understanding of compiler design concepts, especially token generation and frequency analysis.
