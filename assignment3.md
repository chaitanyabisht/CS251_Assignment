# Assignment 3 - Intermediate Code Generation

## Steps to run the code

```
$ lex parse.l
$ yacc parse.y
$ gcc append.c
$ ./a.out test_code.c > output.c
$ gcc y.tab.c -lfl
$ ./a.out output.c
```

OR

__Use the shell script I provided by `./script.sh` which executes all the commands mentioned above for you.__

---

If you want to test the program for the code of your choice, 
- Open the file `test_code.c` in a text editor and add the code of your choice.
- Repeat the steps mentioned above
