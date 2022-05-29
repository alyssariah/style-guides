# Javascript Style Guide

## Table of Contents
1. [Naming Conventions](#naming-conventions)
2. [Whitespace](#whitespace)
3. [Statements](#statements)
4. [Blocks](#blocks)
5. [Quotes](#quotes)
6. [Local variable declarations](#local-variable-declarations)
7. [Arrays](#arrays)
8. [Objects](#objects)
9. [Functions](#functions)
10. [Loops](#loops)
11. [Comparison Operators](#comparison-operators)
12. [Comments](#comments)

## Naming Conventions

- Avoid single letter names. Be descriptive with your naming.

        // Not Recommended
        function q() {
            //..stuff..
        }

        //Recommended
        function query() {
            //..stuff..
        }

- File names must be all `lowercase` and may include underscores (\_) or dashes (-), but no additional punctuation. Follow the convention that your project uses. Filenames’ extension must be .js.

- Object, function, and instance names are written in `lowerCamelCase`

- Parameter names are written in `lowerCamelCase`

- Local variable names are written in `lowerCamelCase`

[Back to top](#javascript-style-guide)

## Whitespace

- Indent all block content with 2 spaces

- Place 1 space before the leading brace in functions and control statements (if, while, ect.).

        // Not Recommended
        if(test){
            console.log('test');
        }

        // Recommended
        if(test) {
            console.log('test');
        }

- Place no space before the argument list in the function calls and declarations

        // Not Recommended
        function test () {
            console.log('test');
        }

        // Recommended
        function test() {
            console.log('test');
        }

- Set off operators with spaces.

        // Not Recommended
        let x=y+5;

        // Recommended
        let x = y + 5;

- Use indentation when making long method chains. Use a leading dot, which emphasizes that the line is a method call, not a new statement.

- Leave a blank line after blocks and before the next statement

        // Not Recommended
        const obj = {
            foo: function () {
            },
            bar: function () {
            }
        };
        return obj;

        // Recommended
        const obj = {
            foo: function () {
            },
            bar: function () {
            }
        };

        return obj;

[Back to top](#javascript-style-guide)

## Statements

- Each statement is followed by a line-break.

- Semicolons are required. Every statement must be terminated with a semicolon. Relying on automatic semicolon insertion is forbidden.

        // Not Recommended
        let name = 'Elon Musk'

        // Recommended
        let name = 'Elon Musk';

[Back to top](#javascript-style-guide)

## Blocks

- Use braces with all multi-line blocks.

- If you're using multi-line blocks with `if` and `else`, put `els`e on the same line as your `if` block's closing brace.

        // Not Recommended
        if (test) {
            // ...stuff...
        }
        else {
            // ...stuff...
        }

        // Recommended
        if (test) {
            // ...stuff...
        } else {
            // ...stuff...
        }

[Back to top](#javascript-style-guide)

## Quotes

- Ordinary string literals are delimited with single quotes ('), rather than double quotes (").

        // Not Recommended
        let name = "Taylor Swift";

        // Recommended
        let name = 'Taylor Swift';

- Strings longer than 100 characters should be written across multiple lines using string concatenation.

[Back to top](#javascript-style-guide)

## Local variable declarations

- Declare all local variables with either const or let. Use const by default, unless a variable needs to be reassigned. The var keyword must not be used.

- Every local variable declaration declares only one variable: declarations such as let a = 1, b = 2; are not used.

- Local variables are not habitually declared at the start of their containing block or block-like construct. Instead, local variables are declared close to the point they are first used (within reason), to minimize their scope.

[Back to top](#javascript-style-guide)

## Arrays

- Include a trailing comma whenever there is a line break between the final element and the closing bracket.

        const values = [
            'first value',
            'second value',
        ];

- Do not use the variadic Array constructor but use the literal syntax for array creation.

        // Not Recommended
        const a1 = new Array(x1, x2, x3);

        // Recommended
        const a1 = [x1, x2, x3];

- Use array push method instead of direct assignment to add items to an array.

        // Not Recommended
        someStack[someStack.length] = 'abracadabra';

        // Recommeded
        someStack.push('abracadabra');

- Array literals may include the spread operator (...) to flatten elements out of one or more other iterables. The spread operator should be used instead of more awkward constructs with Array.prototype. There is no space after the ....

        [...foo]   // preferred over Array.prototype.slice.call(foo)
        [...foo, ...bar]   // preferred over foo.concat(bar)

- When you need to copy an array, use the slice method on an array.

        let itemsCopy = [];

        // Not Recommended
        for (let i = 0; i < items.length; i++) {
            itemsCopy[i] = items[i];
        }

        // Receommeded
       itemsCopy = items.slice();

[Back to top](#javascript-style-guide)

## Objects

- Do not use the Object constructor but the literal syntax for object creation:

        // Not Recommended
        let item = new Object();

        // Recommended
        let item = {};

- Do not mix quoted and unquoted keys.

- Do not use reserved words as keys.

        // Not Recommended
        let superman = {
            default: { clark: 'kent' },
            private: true
        };

        // Recommended
        let superman = {
            defaults: { clark: 'kent' },
            hidden: true
        };

- Use dot notation when accessing properties.

        // Not Recommended
        let isJedi = luke['jedi'];

        // Recommended
        var isJedi = luke.jedi;


## Functions

- Arrow functions provide a concise function syntax and simplify scoping this for nested functions. Prefer arrow functions over the function keyword, particularly for nested functions.

> Tip: Always using parentheses even for single-parameter arrow functions can avoid situations where adding parameters, but forgetting to add parentheses, may result in parseable code which no longer works as intended.

- Function calls may use the spread operator (...). Prefer the spread operator to Function.prototype.apply when an array or iterable is unpacked into multiple parameters of a variadic function. There is no space after the ....

- Never name a parameter arguments. This will take precedence over the arguments object that is given to every function scope.

[Back to top](#javascript-style-guide)

## Loops

- With ES6, the language now has three different kinds of for loops. All may be used, though for-of loops should be preferred when possible.

[Back to top](#javascript-style-guide)

## Comparison Operators

- Use `===` and `!==` over `==` and `!=`.

- Use shortcuts.

        // Not Recommended
        if (name !== '') {
            // ...stuff...
        }

        // Recommended
        if (name) {
            // ...stuff...
        }

        // Not Recommended
        if (collection.length > 0) {
            // ...stuff...
        }

        // Recommended
        if (collection.length) {
            // ...stuff...
        }

[Back to top](#javascript-style-guide)

## Comments

- Block comments are indented at the same level as the surrounding code. They may be in /_ … _/ or //-style. For multi-line /_ … _/ comments, subsequent lines must start with _ aligned with the _ on the previous line, to make comments obvious with no extra context.

- Use /\*_ ... _/ for multi-line comments. Include a description, specify types and values for all parameters and return values.

        // Recommended
        /**
         * make() returns a new element
         * based on the passed in tag name
         *
         * @param {String} tag
         * @return {Element} element
         */
        function make(tag) {

          // ...stuff...

          return element;
        }

- Use // for single line comments. Place single line comments on a newline above the subject of the comment. Put an empty line before the comment.

- Use // FIXME: to annotate problems.

- Use // TODO: to annotate solutions to problems.

[Back to top](#javascript-style-guide)
