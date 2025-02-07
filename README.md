# JavaScript Closure Issue in setTimeout Loop

This repository demonstrates a common closure-related bug in JavaScript when using `setTimeout` within a loop. The issue stems from how closures capture variables in JavaScript, leading to unexpected results. 

## Bug Description
The provided `bug.js` file contains a function `myFunction` that uses a `for` loop and `setTimeout` to log numbers from 0 to 9. Due to closure behavior, the loop completes before the `setTimeout` callbacks execute, resulting in each callback referencing the final value of `i` (which is 10).  Consequently, all the callbacks log '10' instead of the expected sequence from 0 to 9.

## Solution
The `bugSolution.js` file provides a corrected version of the code. By using an immediately invoked function expression (IIFE) or `let` in a loop, we create a new scope for each iteration, ensuring each `setTimeout` callback captures the correct value of `i`. 

## How to run
1. Clone the repository.
2. Open the `bug.js` and `bugSolution.js` files in a browser's developer console or use a node.js environment to run them.
3. Observe the output difference between the buggy and fixed versions.