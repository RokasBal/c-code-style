# My C style and coding rules

This document describes C code style used by Rokas Baliutavičius in his projects and libraries.

## Table of Contents

- [General rules](#general-rules)
- [Variables](#variables)
- [Functions](#functions)
- [Structures](#structures)
- [Compound statements](#compound-statements)


## General rules

- Use tabs for indentations
- Use 1 tab per indent level
- Do not put spaces between keyword and opening bracket
```c
/* OK */
if(condition)
while(condition)
for(init; condition; step)

/* Wrong */
if (condition)
while (condition)
for (init;condition;step)
```
- Put a space before and after keyword and curly bracket
- Do not put a space between a closing bracket and opening curly bracket

```c
/* OK */
if(){} else {}
do {} while()

/* Wrong */
if(){}else{}
do{}while()
if (){}else{}
```
- Opening curly bracket is always at the same line as keyword, without a space between closing bracket (`for`, `while`, `do`, `switch`, `if`, ...)
```c
int i;
for(i = 0; i < 5; ++i){           /* OK */
}
for(i = 0; i < 5; ++i) {            /* Wrong */
}
for (i = 0; i < 5; ++i)             /* Wrong */
{
}
```

- Do not use space between function name and opening bracket
```c
int32_t a = sum(4, 3);              /* OK */
int32_t a = sum (4, 3);             /* Wrong */
```
- Do not use `stdbool.h` library. Use `1` or `0` for `true` or `false` respectively
```c
/* OK */
uint8_t status;
status = 0;

/* Wrong */
#include <stdbool.h>
bool status = true;
```
- Always use `<` and `>` for C Standard Library include files, eg. `#include <stdlib.h>`
- Always use `""` for custom libraries, eg. `#include "myLibrary.h"`
- Always use brackets with `sizeof` operator
- Use // for single-line comments, and /* */ for multi-line commnents

 ## Variables

- Use English names/text for functions, variables, comments
- Capitalize every word after the first when naming variables (Camel Case)
- Always declare local variables at the beginning of the block, before first executable statement
- Declare pointer variables with asterisk aligned to type
```c
/* OK */
char* a;

/* Wrong */
char *a;
char * a;
```
- When declaring multiple pointer variables, you may declare them with asterisk aligned to variable name
```c
/* OK */
char *p, *n;
```

 ## Functions

- Every function which may have access from outside its module, MUST include function *prototype* (or *declaration*)
- If a function name contains multiple words, every word after the first one needs to be capitalized (Camel Case)
```c
/* OK */
void myFunc(void);
void myFunc();

/* Wrong */
void my_func(void);
void myfunc(void);
void MyFunc();
```
- Use single space before and after comparison and assignment operators
```c
a = 3 + 4;              /* OK */
for(a = 0; a < 5; ++a) /* OK */
a=3+4;                  /* Wrong */
a = 3+4;                /* Wrong */
for(a=0;a<5;++a)       /* Wrong */
```
- Use single space after every comma
```c
func_name(5, 4);        /* OK */
func_name(4,3);         /* Wrong */
```
- When function returns pointer, align asterisk to return type
```c
/* OK */
const char* my_func(void);
my_struct_t* my_func(int32_t a, int32_t b);

/* Wrong */
const char *my_func(void);
my_struct_t * my_func(void);
```

## Structures

- Structure names must be capitalized
- If a structure name is made up from multiple words, each of them also need to be capitalized
- Structure or enumeration may contain `typedef` keyword

## Compound statements

- Every compound statement MUST include opening and closing curly bracket, even if it includes only `1` nested statement
- Every compound statement MUST include single indent; when nesting statements, include `1` indent size for each nest
```c
/* OK */
if(c){
    do_a();
} else {
    do_b();
}

/* Wrong */
if(c)
    do_a();
else
    do_b();

/* Wrong */
if(c) do_a();
else do_b();
```
- In case of `if` or `if-else-if` statement, `else` MUST be in the same line as closing bracket of first statement
```c
/* OK */
if(a){

} else if(b){

} else {

}

/* Wrong */
if(a){

}
else {

}

/* Wrong */
if(a){

}
else
{

}
```
- In case of `do-while` statement, `while` part MUST be in the same line as closing bracket of `do` part
```c
/* OK */
do {
    int32_t a;
    a = do_a();
    do_b(a);
} while(check());

/* Wrong */
do
{
/* ... */
} while(check());

/* Wrong */
do {
/* ... */
}
while(check());
```

- Indentation is REQUIRED for every opening bracket
```c
if(a){
    do_a();
} else {
    do_b();
    if(c){
        do_c();
    }
}
```

