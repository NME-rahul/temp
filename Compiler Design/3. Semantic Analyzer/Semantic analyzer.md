# Semantic analyzer
The third pase of cmpiler design, it make sures that declaration and statements of program are sematically correct. It uses syntax tree to check semantics of program.

### Semtaic Errors

1. Type(data type) mismatch
   * Each Declared variable and its assigned value must have same data type
2. Undeclared Variables
   * Use of variables that is not declared yet.
3. Use of reserved keywords
   * Use of reseverd keywords like ```if-else``` as the variable's name.
4. Flow control check
   * Every ```else``` should precede with ```if``` block.
   * ```break``` statements must not be outside the loop.
