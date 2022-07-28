# dude-ebnf

## Symbols
```
<digit-separator>                   ::= "'"
<binary-digit>                      ::= <digit-separator> | "0" | "1"
<decimal-digit>                     ::= <binary-digit> | "2" | "3" | "4" | "5" | "6" | "7" | "8" | "9"
<hex-digit>                         ::= <decimal-digit> | "A" | "B" | "C" | "D" | "E" | "F"

<binary-number>                     ::= "0b"<binary-digit>+
<decimal-number>                    ::= <decimal-digit>+
<hex-number>                        ::= "0x"<hex-digit>+
<floating-number>                   ::= <decimal-number> "." <decimal-number> ( "E" ( "+" | "-" ) <decimal-number> )?
<number>                            ::= <binary-number> | <decimal-number> | <hex-number>


<lower-letter>                      ::= "a" | "b" | "c" | "d" | "e" | "f" | "g" | "h" | "i" | "j" | "k" | "l" | "m" | 
                                        "n" | "o" | "p" | "q" | "r" | "s" | "t" | "u" | "v" | "w" | "x" | "y" | "z"
<upper-letter>                      ::= "A" | "B" | "C" | "D" | "E" | "F" | "G" | "H" | "I" | "J" | "K" | "L" | "M" | 
                                        "N" | "O" | "P" | "Q" | "R" | "S" | "T" | "U" | "V" | "W" | "X" | "Y" | "Z"
<letter>                            ::= <lower-letter> | <upper-letter>
<identifier-symbol>                 ::= "_" | <letter>
```

## Comments
```
<line-comment>                      ::= "//"
<multiline-comment>                 ::= "/*" ... "*/"
```

## Keywords
```
<keyword>                           ::= "fun" | "ret" | "end" | "if" | "elif" | "else" | "nop"
```

## Operators
```
<math-operator>                     ::= "+" | "-" | "/" | "*" | "//" | "**" | "%"
<boolean-operator>                  ::= "<" | ">" | "<=" | ">=" | "==" | "!=" | "!=" | "&&" | "||"
<binary-operator>                   ::= "&" | "|" | "~" | "^"
<assignment-operator>               ::= "="
<const-assignment-operator>         ::= ":="
```

## Conditions
```
<condition>                         ::= <if-statement> <elif-statment>? <else-statement>? "end"? 
<if-statement>                      ::= "if" <boolean-statement> <statement> 
<elif-statement>                    ::= "elif" <boolean-statement> <statement>
<else-statement>                    ::= "else" <statement> 
```

## Loops
```
<for-loop>                          ::= "for" <identifier> "in" <expression> "end" 
```

## Function
```
<function>                          ::= <named-function> | <inline-function>
<named-function>                    ::= "fun" <identifier> <function-parameters> <function-body>
<inline-function>                   ::= "fun" <function-parameters> <function-body>
<function-parameters>               ::= "(" ( <identifier> ( "," <identifier> )* )? ")"
<function-body>                     ::= <statement>+

<anonymous-function>                ::= ... ~= lambda
```

## Statements
```
<statement>                         ::= <empty-statement> | <return-statement> | <expression> | <assignment-statement>
<empty-statement>                   ::= "nop" 
<return-statement>                  ::= "ret" 
<assignment-statement>              ::= <identifier> <assignment-operator> <expression>
<expression>                        ::= <identifier> | <number> | <function>
```

## bla
```
<identifier>                        ::= <identifier-symbol> ( <identifier-symbol> | <decimial-digit> )*
<program>                           ::= <statement>*  
```
