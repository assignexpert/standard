# CODE

This document describes how code should be written.

## whitespace

Use spaces only, no tabs. Keep indentation of your code to 4 spaces. If you have a preference of using tabs, make sure that the editor that you use is configured to map the tabs to spaces.

Maintain a single whitespace:
1. after writing a reserved keyword such as `for`, `if`, `else`, `try`, `catch`. 
2. on both sides of the colon in an enhanced for ("foreach") statement.
3. on both sides of any binary or ternary operator.

## braces

Braces are used with `if`, `else`, `for`, `do` and while statements, even when the body is empty or contains only a single statement. 

## blocks

Braces follow the Kernighan and Ritchie style ("Egyptian brackets") for nonempty blocks and block-like constructs:

1. No line break before the opening brace.
2. Line break after the opening brace.
3. Line break before the closing brace.
4. Line break after the closing brace, only if that brace terminates a statement or terminates the body of a method, constructor, or named class. 

```javascript
function doSomething() {

    doMoreWork();
    if (condition()) {
        workHere();
    }
    else {
        workThere();
    }
}
```
 
#### for empty blocks: 
```javascript
// cool
function emptyBlock() {}

// cool
function emptyBlock() {
}

// not cool
function emptyBlock() {

}
```

### indent blocks by 4 spaces

Each time a new block or block-like construct is opened, the indent increases by four spaces. When the block ends, the indent returns to the previous indent level.
<br>
<hr>
<br>

## column limit: 100 characters

A "character" means any Unicode code point. Except as noted below, any line that would exceed this limit must be line-wrapped. (When code that might otherwise legally occupy a single line is divided into multiple lines, this activity is called line-wrapping.)

`import` statements are an exception to the above rule.

When line-wrapping, each line after the first (each continuation line) is indented at least +4 from the original line.
<br>
<hr>
<br>

## variables

One variable per declaration. Every variable declaration (field or local) declares only one variable. The following kind of declaration should be avoided:
```java
int a, b;
```
*Exception*: Multiple variable declarations are acceptable in the header of a `for` loop. 
 
Declare when needed. Local variables are not habitually declared at the start of their containing block or block-like construct. Instead, local variables are declared close to the point they are first used (within reason), to minimize their scope.

## nomenclature

1. *Method/Variable*: `lowerCamelCase`
2. *Class*: `UpperCamelCase`
3. *Constant*: All uppercase letters, with each word separated from the next by a single underscore.
4. Try to make names meaningful. Function names should ideally be verbs because a function does something.

## comments

1. For single-line comments, use any form. (/\*...\*/ or //) 
2. For multi-line comments, just use /\*...\*/

## further...

It would be helpful to all of us as a whole if you stick to these guidlines. However, this document is far from being complete. There might be many more things that can be incorporated. Our codebase would also make use of linters and tools like [Prettier](https://prettier.io/) to improve code quality. During pull request reviews, the maintainer might suggest some changes. Please be receptive of the feedback. The feedback is for the code, not for you as a person. The collective aim is to write high-quality maintainable software.

