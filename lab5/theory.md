# Syntax Analyzer for IF-ELSE Statements using Flex and Bison
## Aim
- To design a syntax analyzer that accepts valid if, if-else, and nested if-else statements.
- To detect syntax errors in the given statements.
- To resolve the dangling-else problem using grammar precedence and associativity rules.
- To parse statements interactively through the command-line interface.

## Software requirements
- Flex	
- Bison	
- GCC	
- Operating System

## Theory
### Flex

Flex is a lexical analyzer generator. It scans the source code character by character and converts it 
into meaningful tokens that can be understood by the parser.

The scanner recognizes tokens such as:
- IF
- ELSE
- ID (Identifier)
- NUM (Number)
- RELOP (Relational Operator)
- ASSIGN (=)
- SEMICOLON (;)

Whitespace characters are ignored, while unknown symbols generate an error message.
### Bison
Bison is a parser generator that uses Context-Free Grammar (CFG) rules to verify whether 
the sequence of tokens produced by Flex follows the syntax of the language.

The parser checks:
- Simple if statements
- if-else statements
- Nested if-else statements
If the input satisfies the grammar, the parser prints "valid"; otherwise, it reports a syntax error.

### Dangling Else Problem
The dangling-else problem occurs when an else clause can be associated with more than one if statement, creating ambiguity.
This ambiguity is resolved using precedence declarations:
- %nonassoc LOWER_THAN_ELSE
- %nonassoc ELSE
The %prec LOWER_THAN_ELSE directive ensures that every else is matched with the nearest unmatched if, eliminating ambiguity.


## Result
The syntax analyzer for if, if-else, and nested if-else statements was successfully implemented using Flex and Bison.
The parser correctly accepts valid statements, rejects invalid syntax, and resolves the dangling-else ambiguity using 
precedence rules. The program demonstrates the integration of lexical analysis and syntax analysis in compiler design.




## Conclusion

This experiment demonstrated the implementation of a syntax analyzer using Flex and Bison. Flex successfully converted the
input into tokens, while Bison validated the token sequence according to the specified Context-Free Grammar. The parser 
effectively handled simple and nested if-else statements, detected syntax errors, and resolved the dangling-else problem 
through precedence declarations. This experiment provides a practical understanding of lexical analysis, parsing techniques, 
and compiler construction.
