# Unexpected Loop Variable Value in setTimeout

This example demonstrates a common issue in JavaScript when using closures within `setTimeout` loops.  The expected behavior is to print numbers 0-9 with a one-second delay between each. However, due to the way closures work, the loop completes before the `setTimeout` callbacks execute, resulting in the value of `i` being 10 for all iterations.

## How to Reproduce

1.  Clone this repository.
2.  Open `bug.js`.
3.  Run the `myFunction()` in your browser's console or a Node.js environment.

You'll observe that the console logs '10' ten times instead of 0-9.

## Solution

The solution involves creating a new variable scope for each iteration using an immediately invoked function expression (IIFE) or using `let` within the `setTimeout` callback (although this is less common in older examples).