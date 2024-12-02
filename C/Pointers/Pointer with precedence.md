<div align="center">

| **Precedence Level** | **Operators**                             | **Description**                               | **Associativity** |
|----------------------|-------------------------------------------|-----------------------------------------------|-------------------|
| 1 (Highest)          | `()` `[]` `->` `.`                       | Function call, array subscript, member access | Left-to-right     |
|                      | `++` `--` (postfix)                      | Post-increment and post-decrement             | Left-to-right     |
| 2                    | `++` `--` `+` `-` `!` `~`                | Unary increment, decrement, positive/negative, logical NOT, bitwise NOT | Right-to-left     |
|                      | `(type)`                                 | Type cast                                     | Right-to-left     |
|                      | `*` `&`                                  | Dereference, address-of                       | Right-to-left     |
|                      | `sizeof`                                 | Size of                                        | Right-to-left     |
|                      | `_Alignof`                               | Alignment                                     | Right-to-left     |
| 3                    | `*` `/` `%`                              | Multiplication, division, modulo              | Left-to-right     |
| 4                    | `+` `-`                                  | Addition, subtraction                         | Left-to-right     |
| 5                    | `<<` `>>`                                | Bitwise shift left, right                     | Left-to-right     |
| 6                    | `<` `<=` `>` `>=`                        | Relational less/greater                       | Left-to-right     |
| 7                    | `==` `!=`                                | Equality, inequality                          | Left-to-right     |
| 8                    | `&`                                      | Bitwise AND                                   | Left-to-right     |
| 9                    | `^`                                      | Bitwise XOR                                   | Left-to-right     |
| 10                   | `|`                                      | Bitwise OR                                    | Left-to-right     |
| 11                   | `&&`                                     | Logical AND                                   | Left-to-right     |
| 12                   | `||`                                     | Logical OR                                    | Left-to-right     |
| 13                   | `? :`                                    | Ternary conditional                           | Right-to-left     |
| 14                   | `=` `+=` `-=` `*=` `/=` `%=`             | Assignment operators                          | Right-to-left     |
|                      | `<<=` `>>=` `&=` `^=` `|=`               | Assignment operators                          | Right-to-left     |
| 15 (Lowest)          | `,`                                      | Comma operator                                | Left-to-right     |

</div>
