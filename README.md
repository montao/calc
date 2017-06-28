# calc
A calculator done with GNU flex and bison. For more information, read the book by John Lexon about flex and bison. 

# instructions

```
developer@1604:~$ git clone https://github.com/montao/calc.git
Cloning into 'calc'...
remote: Counting objects: 13, done.
remote: Compressing objects: 100% (12/12), done.
remote: Total 13 (delta 2), reused 0 (delta 0), pack-reused 0
Unpacking objects: 100% (13/13), done.
Checking connectivity... done.
developer@1604:~$ cd calc/
developer@1604:~/calc$ make
bison -d fb1-5.y
flex fb1-5.l
cc -o fb1-5 fb1-5.tab.c lex.yy.c -lfl
fb1-5.tab.c: In function ‘yyparse’:
fb1-5.tab.c:1123:16: warning: implicit declaration of function ‘yylex’ [-Wimplicit-function-declaration]
       yychar = yylex ();
                ^
fb1-5.tab.c:1288:7: warning: implicit declaration of function ‘yyerror’ [-Wimplicit-function-declaration]
       yyerror (YY_("syntax error"));
       ^
fb1-5.y: At top level:
fb1-5.y:29:1: warning: return type defaults to ‘int’ [-Wimplicit-int]
 main(int argc, char **argv)
 ^
fb1-5.y:33:1: warning: return type defaults to ‘int’ [-Wimplicit-int]
 yyerror(char *s)
 ^
developer@1604:~/calc$ ls
fb1-5    fb1-5.tab.c  fb1-5.y   Makefile
fb1-5.l  fb1-5.tab.h  lex.yy.c  README.md
developer@1604:~/calc$ ./fb1-5 
1+2+3*4
= 15
```
