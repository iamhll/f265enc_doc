.. -----------------------------------------------------------------------------
  ..
  ..  Filename       : main.rst
  ..  Author         : Huang Leilei
  ..  Created        : 2020-07-12
  ..  Description    : coding style related documents
  ..
.. -----------------------------------------------------------------------------

Coding Style
============

Basic Rules
-----------

revised from
https://www.kernel.org/doc/html/latest/process/coding-style.html
and https://bitbucket.org/multicoreware/x265/wiki/Coding

#.  Indentation

    use 4 spaces

    ::

        if (condition) {
            statements
        }
        else {
            statements
        }

#.  Breaking long lines and strings

    keep lines within 80 characters.

    \

#.  Placing Braces and Spaces

    for all non-function statement blocks,
    put the opening brace last on the line, and put the closing brace first

    ::

        if (condition) {
            statements
        }
        else {
            statements
        }

    for functions,
    put the opening brace at the beginning of the next line

    ::

        int function(int variable)
        {
            statements;
        }

    for single statement,
    omit braces

    ::

        if (condition)
            one statement;
        else
            one statement;

    but for the following cases,
    still keep them

    ::

        if (condition) {
            one statement;
            one statement;
        }
        else {
            one statement;
        }

    ::

        if (condition) {
            if (condition) {
                if (condition)
                    statement
            }
        }

#.  Spaces

    use a space after the follwing keywords

    ::

        if, switch, case, for, do, while

    but not with the following keywords

    ::

        sizeof, typeof, alignof, __attribute__

    do not add spaces around parenthesized expressions

    ::

        if (condition)

    adjacent * to the data name or function name

    ::

        int *variable;
        int *function(int variable);

    use one space on each side of the follwing operators
    (where, &, \*, ... are used as binary or ternary operators)

    ::

        =, +, -, <, >, *, /, %, |, &, ^, <=, >=, ==, !=, ?, :

    do not use space after the following operators
    (where, &, \*, ... are used as unary operators)

    ::

        &, *, +, -, ~, !, sizeof, typeof, alignof, __attribute__, defined

    do not use space before the postfix increment or decrement unary operators

    ::

        ++, --

    do not use space after the prefix increment or decrement unary operators

    ::

        ++, --

    do not use space around member operators

    ::

        ., ->

    do not leave trailing whitespace at the ends of lines

    \

#.  Naming

    use small camel case for variables or functions

    ::

        int datCst
        int getPre()

    use big camel case or small camel case with postfix _t for type

    ::

        Pixel* pxlRec
        pxl_t* pxlRec

    use big camel case or capitalization for class

    ::

        int Encoder::run()
        int RMD::run()

    use big camel case or capitalization for defintions or enums

    ::

        #define MACRO    value
        enums class typCst_t{
            SAD_D = 0,
            SATD_R
        }

    use the following prefix or postfix to indicate variable types

    ::

        m_, class member
        s_, static class member
        g_, global variables
        b, boolen varibles (could be ommitted for names like flgSplit)
        _t, defined types

.. #.  Typedefs
..
.. #.  Functions
..
.. #.  Commenting
..
.. #.  You’ve made a mess of it
..
.. #.  Kconfig configuration files
..
.. #.  Data structures
..
.. #.  Macros, Enums and RTL
..
.. #.  Printing kernel messages
..
.. #.  Allocating memory
..
.. #.  The inline disease
..
.. #.  Function return values and names
..
.. #.  Using bool
..
.. #.  Don't re-invent the kernel macros
..
.. #.  Editor modelines and other cruft
..
.. #.  Inline assembly
..
.. #.  Conditional Compilation


Supplemental Rules
------------------

collected through code review

#.  Indentation

    never use tab

#.  **Definition**

    must be atomic

    ::

        #define C    A + B      // wrong

    ::

        #define C    (A + B)    // right
