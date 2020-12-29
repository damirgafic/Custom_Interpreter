# Custom_Interpreter
[![made-with-Java](https://img.shields.io/badge/Made%20With-Java-blue?logo=appveyor&style=Java)](https://www.python.org/)
![made-with-Java](https://img.shields.io/appveyor/build/damirgafic/custom-interpreter)<br />
This is a custom interpreter I made using Java that takes in raw source code as a series of characters and groups it into a series of chunks called tokens. 
The main method for this interpreter to do what it does is the scanner. This program can be run by typing
``` javac Lox.java filename.txt ```
or you can type code
in the command line interactively with the interpreter by just typing  
``` javac Lox.java ```
in the command line. 

When Lexical Analysis has begun the program will scan through the file identifying lexemes. From there we have to identify the type of token, and 
whether there are more lexemes to follow that create a different token than what is immediately identified. The scanner is a switch statement that can identify 
single-character lexemes as well as multi-character lexemes. There are special case to differentiate between a single ```!``` and a ```!=```. Reserved words were 
handled by defining the set in a map.

Currently my program identifies the type of token the lexeme is. 
```
> print "Hello, world!";
t = true;  // A comment
f = false; //
num1 = 5;
num2 = 5;
num1 = num1 + num2;
num1 = num1/num2;

var a = 0;
while (a < 5) {
  print a;
}

fun returnSum(a, b) {
  return a + b;
}
returnSum(10,10);

PRINT print null
STRING "Hello, world!" Hello, world!
SEMICOLON ; null
EOF  null
> IDENTIFIER t null
EQUAL = null
TRUE true null
SEMICOLON ; null
EOF  null
> IDENTIFIER f null
EQUAL = null
FALSE false null
SEMICOLON ; null
EOF  null
> IDENTIFIER num1 null
EQUAL = null
NUMBER 5 5.0
SEMICOLON ; null
EOF  null
> IDENTIFIER num2 null
EQUAL = null
NUMBER 5 5.0
SEMICOLON ; null
EOF  null
> IDENTIFIER num1 null
EQUAL = null
IDENTIFIER num1 null
PLUS + null
IDENTIFIER num2 null
SEMICOLON ; null
EOF  null
> IDENTIFIER num1 null
EQUAL = null
IDENTIFIER num1 null
SLASH / null
IDENTIFIER num2 null
SEMICOLON ; null
EOF  null
> EOF  null
> VAR var null
IDENTIFIER a null
EQUAL = null
NUMBER 0 0.0
SEMICOLON ; null
EOF  null
> WHILE while null
LEFT_PAREN ( null
IDENTIFIER a null
LESS < null
NUMBER 5 5.0
RIGHT_PAREN ) null
LEFT_BRACE { null
EOF  null
> PRINT print null
IDENTIFIER a null
SEMICOLON ; null
EOF  null
> RIGHT_BRACE } null
EOF  null
> EOF  null
> FUN fun null
IDENTIFIER returnSum null
LEFT_PAREN ( null
IDENTIFIER a null
COMMA , null
IDENTIFIER b null
RIGHT_PAREN ) null
LEFT_BRACE { null
EOF  null
> RETURN return null
IDENTIFIER a null
PLUS + null
IDENTIFIER b null
SEMICOLON ; null
EOF  null
> RIGHT_BRACE } null
EOF  null
> EOF  null
> IDENTIFIER returnSum null
LEFT_PAREN ( null
NUMBER 10 10.0
COMMA , null
NUMBER 10 10.0
RIGHT_PAREN ) null
SEMICOLON ; null
EOF  null
> 
```
