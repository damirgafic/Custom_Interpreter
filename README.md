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
