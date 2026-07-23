# Computation of FIRST and FOLLOW Sets Using C
## Objective
- To design and implement a C program for computing the FIRST and FOLLOW sets of a Context-Free Grammar (CFG).
- To understand the role of FIRST and FOLLOW sets in compiler syntax analysis.
- To compute the FIRST set for each non-terminal symbol in the given grammar.

## Theory
A compiler performs syntax analysis after lexical analysis to verify whether the sequence of tokens follows the
grammar rules of a programming language. To make parsing efficient and deterministic, the compiler computes the
FIRST and FOLLOW sets of every non-terminal symbol.

### FIRST Set
The FIRST(X) of a grammar symbol X is the set of terminal symbols that can appear as the first symbol in any string
derived from X. If X can derive an empty string (ε), then ε is also included in its FIRST set. In this implementation,
epsilon is represented by the character 'e'.

### FOLLOW Set
The FOLLOW(A) of a non-terminal A is the set of terminal symbols that can immediately appear to the right of A in some 
sentential form. If A is the start symbol, the end marker $ is automatically included in its FOLLOW set.

## Conclusion
The experiment successfully implemented a C program to compute the FIRST and FOLLOW sets of a context-free grammar.
The iterative approach accurately computes the required sets by repeatedly processing grammar productions until no 
further changes occur. The resulting FIRST and FOLLOW sets provide the essential information needed for constructing 
predictive parsing tables in LL(1) parsers and form a fundamental component of syntax analysis in compiler design. 
The experiment also strengthened understanding of grammar processing, parser construction, and the role of FIRST and 
FOLLOW sets in efficient, deterministic parsing.
