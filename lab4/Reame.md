# Arithmetic Expression Evaluator Using Flex and Bison
## Objectives
  - To design and implement a lexical analyzer and parser using Flex and Bison for evaluating arithmetic expressions.
  - To understand and apply grammar rules, operator precedence, and semantic actions for performing expression evaluation and error handling.

## Theory
 Lexical analysis and syntax analysis are two important phases of compiler design used to process and understand programming languages.

In this experiment, Flex is used to perform lexical analysis, where the input expression is broken into meaningful tokens such as numbers, operators (+, -, *, /), and parentheses. These tokens are then passed to the parser.

Bison is used for syntax analysis. It defines a context-free grammar that specifies how tokens can be combined to form valid arithmetic expressions. The parser checks whether the input follows the correct grammar rules and evaluates the expression using semantic actions.

The grammar is designed to handle:

-Operator precedence (* and / have higher priority than + and -)
-Left associativity of operators
-Parentheses to override default precedence

During parsing, semantic actions are used to compute intermediate and final results. The system also includes error handling mechanisms such as detection of division by zero and invalid syntax.

## Result

The parser correctly evaluates arithmetic expressions while respecting operator precedence, where multiplication and division are performed before addition and subtraction, as well as correctly handling expressions with parentheses. It also safely detects and handles division by zero and reports syntax errors clearly to the user.

## Conclusion

In this experiment, we learned how to use Bison to define grammar rules for arithmetic expression evaluation and how Flex performs tokenization to pass valid tokens to the parser. As a result, we successfully built a working calculator that evaluates expressions correctly and handles invalid inputs and runtime errors effectively.
