# Lexical Analyzer for C language

The analyzer breaks down the given statements into tokens and tries to give additional details about the tokens itself.

These 8 examples tries to cover all the required programming constructs as required.

# How to use it ?

Compile the .l(Lex) file to .c file using flex
```
flex tokenizer.l
```

Compile the .c file using GCC
```
gcc lex.yy.c
```
Run the binary
```
./a.out
```
Give one statement at a time and then press enter, to exit the program press enter twice.

## Example 1: Declaring an integer

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: unsigned int x = 1;
unsigned int    Data Type
x       Identifier       
=       Operator
1       Number
;       Separator
```

## Example 2: Declaring a floating point number

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: float y = 9.4123;
float   Data Type
y       Identifier
=       Operator
9.4123  Floating Point Number
;       Separator

```

## Example 3: Writing an if statement

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: if (x == 0) return false;
if      Conditional Flow
(       Separator
x       Identifier
==      Operator
0       Number
)       Separator
return  Keyword
false   Boolean Value
;       Separator
```
## Example 4: Writing a comment

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: // This is a comment
// This is a comment    Comment
```
```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: /* This is also a comment */
/* This is also a comment */    Comment

```

## Example 5: Defining a function

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: int main()
++++++++++++++++++++++++++++++++++++++++++++++
int main()      Function Definition
int     Data Type
(       Separator
)       Separator
++++++++++++++++++++++++++++++++++++++++++++++
```

## Example 6: Calling a function

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: main() 
++++++++++++++++++++++++++++++++++++++++++++++
main()  Function Invocation
(       Separator
)       Separator
++++++++++++++++++++++++++++++++++++++++++++++

```

## Example 7: Defining structs

For example, if a struct is defined previously in a statement, then the analyzer remembers that and when an object with that struct type is declared, it catches that and tells that it is a user defined structure.

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out

Enter String: struct Pair{int x,y;}
++++++++++++++++++++++++++++++++++++++++++++++
struct  Structure
Pair    Identifier
++++++++++++++++++++++++++++++++++++++++++++++
{       Separator 
int     Data Type 
x       Identifier
,       Separator 
y       Identifier
;       Separator
}       Separator

Enter String: Pair x = {1,2};

Pair    User defined Structure
x       Identifier
=       Operator
{       Separator
1       Number
,       Separator
2       Number
}       Separator
;       Separator

```

## Example 8: Defining strings

```
cbisht@chait-laptop:~/chait/study/CS251/Assignment1$ lex tokenizer.l && gcc lex.yy.c  && ./a.out
Enter String: char* s = "hello";
char    Data Type     
*       Operator      
s       Identifier    
=       Operator      
"hello" String Literal
;       Separator     
```

