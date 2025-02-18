# Incorrect comparison of objects with functions in TypeScript

This repository contains a TypeScript function that incorrectly compares objects that contain functions. The bug is that the function uses a strict equality check to compare objects, which means that the objects will only be considered equal if they are the same object in memory. However, functions are not compared by their contents but by reference.  Therefore, two objects that have the same function values will be compared as unequal. This bug is demonstrated by the test cases provided.

## Bug

The bug is in the `compareObjects` function.  It does not properly handle function properties.

## Solution

The solution involves customizing the comparison to handle functions by comparing function bodies, using a string representation to compare functions based on their implementation. However, this approach introduces its own considerations around comparing function closures and dynamic contexts which are out of scope for this simplified solution.

## How to reproduce

1. Clone the repository.
2. Compile the code using `tsc bug.ts`.
3. Run the tests with `node bug.js` (after running the command `tsc bug.ts`).