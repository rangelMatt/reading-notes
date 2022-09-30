# Operators and Loops

## Loops and iterations

Loops offer a quick and easy way to do something repeatedly.

A loop is a computerized version of the game where you tell someone to take X steps in one direction, and Y steps in another. The below is an idea to "Go five steps to the east" as a loop.

> for (let step = 0; step < 5; step ++) {
> // Runs 5 times, with values of step 0 through 4.
>console.log ('Walking east one step');
>}

There are many different types of loops, but they do the same thing: repeat an action some number of times.

There are various situations that are more easily serve dby one type of loop over the others. Various loop mechanisms offer different wayt to determine the start and end points of the loop.

Statements for loops provided in JS are:

* [for statement](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for_statement>)
* [do...while statement][(<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#do...while_statement>)]
* [while statement][(<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#while_statement>)]
* [labeled statement](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#labeled_statement>)
* [break statement](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#break_statement>)
* [continue statement](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#continue_statement>)
* [for...in statement](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...in_statement>)
* [for of statement](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Loops_and_iteration#for...of_statement>)

### For statement

A for loop repeats until a specified condition evaluates to `false`. The JavaScript `for` loop is similar to the Java and C `for` loop.

### While statement

A while statement executes its statements as long as a specified condition evaluates `true`. A `while` statement looks as follows:

> while (condition)
> statement

If the `condition` becoms `false`, `statement` within the loop stops executing and control passes to the statement following the loop.

The condition test occurse *before* `statement` in the loop is executed. If the condition returns `true`, `statement` is executed and the *`condition`* is tested again. If the condition returns `false`, execution stops, and control is passed tot he statement following `while`.

### Example

>let n = 0;
>let x = 0;
>while (n < 3) {
>n++;
>x += n;
>}

### break statement

Use the [break](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/break>) statement to terminate a loop, `switch`, or in conjunction with a labeled statement.

### `continue` statement

The [continue](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/continue>) statement can be used to restart a `while`, `do-while`, `for`, or `label` statement.

### `for...in` statement

The [for...in](<https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Statements/for...in>) statement iterates a specified variable over all the enumerable properties of an object. For each distinct propert, JavaScript executes the specified statements. A `for...in` statement looks as follows:

>for (variable in object)
>statement

[<---BACK](README.md)