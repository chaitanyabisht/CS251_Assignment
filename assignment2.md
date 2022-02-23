# CS251 Assignment 2 Documentation

Compile the code with the following commands:

```
$ bison -d syntax.y
$ flex lex.l
$ gcc syntax.tab.c lex.yy.c
$ ./a.out 
```

# Testing our Parser

## Method 1 (For single line code)
```
$ ./a.out
Enter Code Snippet:
int x = 1;
PASS: code is syntactically sound.
```

## Method 2 (For multi line code)

`$ ./a.out < YOUR_CODE.c `

This takes the whole .c code and parses the code line by line. The parser halts when it detects a syntax error.

# Examples

## Example 1

```
$ ./a.out
Enter Code Snippet:
int int x = 1;
ERROR: multiple primitive data-types found.
```

## Example 2

Here is the code for `code1.c`

```
#include <iostream>
int main(){
        int x = 1;
        if (x == 1){
                return 0;
        }

}
```
Running our parser on the above code

```
$ ./a.out < code1.c
Enter Code Snippet:
PASS: code is syntactically sound.

```

## Example 3

Here is the code for `code2.c`

```
#include <iostream>

int main(){

        float x = 1;

        for (int i = 0; i < 50; ++i){
                printf("hello\n");
        }

}
```
Running our parser on the above code

```
$ ./a.out < code2.c
Enter Code Snippet:
PASS: code is syntactically sound.

```
