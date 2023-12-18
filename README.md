# My C style and coding rules

This document describes C code style used by Rokas Baliutavičius in his projects and libraries.

## Table of Contents

- [General rules](#general-rules)
- [Variables](#variables)


## General rules

- Use tabs for indentations
- Use 1 tab per indent level
- Do not put spaces between keyword and pening bracket
```c
/* OK */
if(condition)
while(condition)
for(init; condition; step)
do{}while(condition)

/* Wrong */
if (condition)
while (condition)
for (init;condition;step)
do {} while (condition)
```
- Put a space before and after keyword and curly bracket

```c
/* OK */
if(){} else {}
do {} while()

/* Wrong */
if(){}else{}
do{}while()
if (){}else{}
```

- Do not use space between function name and opening bracket
```c
int32_t a = sum(4, 3);              /* OK */
int32_t a = sum (4, 3);             /* Wrong */
```
- Always use `<` and `>` for C Standard Library include files, eg. `#include <stdlib.h>`
- Always use `""` for custom libraries, eg. `#include "my_library.h"`
- Always use brackets with `sizeof` operator
- Use '//' for single-line comments, and '/* comment */' for multi-line commnents

 ## Variables

- Capitalize every word after the first when naming variables (Camel Case)
- Opening curly bracket is always at the same line as keyword, without a space between closing bracket (`for`, `while`, `do`, `switch`, `if`, ...)
```c
size_t i;
for(i = 0; i < 5; ++i){           /* OK */
}
for(i = 0; i < 5; ++i) {            /* Wrong */
}
for (i = 0; i < 5; ++i)             /* Wrong */
{
}
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

- Always declare local variables at the beginning of the block, before first executable statement
- Do not use `stdbool.h` library. Use `1` or `0` for `true` or `false` respectively
```c
/* OK */
uint8_t status;
status = 0;

/* Wrong */
#include <stdbool.h>
bool status = true;
```

- Use English names/text for functions, variables, comments
- 
