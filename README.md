# My C style and coding rules

This document describes C code style used by Rokas Baliutavičius in his projects and libraries.

## Table of Contents

- [Recommended C style and coding rules](#recommended-c-style-and-coding-rules)
  - [Table of Contents](#table-of-contents)
  - [The single most important rule](#the-single-most-important-rule)
  - [Integration with VSCode](#integration-with-vscode)
  - [Conventions used](#conventions-used)
  - [General rules](#general-rules)
  - [Comments](#comments)
  - [Functions](#functions)
  - [Variables](#variables)
  - [Structures, enumerations, typedefs](#structures-enumerations-typedefs)
  - [Compound statements](#compound-statements)
    - [Switch statement](#switch-statement)
  - [Macros and preprocessor directives](#macros-and-preprocessor-directives)
  - [Documentation](#documentation)
  - [Header/source files](#headersource-files)
  - [Clang format integration](#clang-format-integration)
  - [Artistic style configuration](#artistic-style-configuration)
  - [Eclipse formatter](#eclipse-formatter)

## General rules

- Use tabs for indentations
- Use '1' tab per indent level
- Do not put spaces between keyword and round or square opening bracket
 
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

  
