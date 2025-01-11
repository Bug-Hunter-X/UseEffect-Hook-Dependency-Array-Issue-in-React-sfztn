# useEffect Hook Dependency Array Issue

This repository demonstrates a common error when using the `useEffect` hook in React: including the state variable in the dependency array, causing infinite loops and unexpected behavior. The solution provides the correct way to handle dependencies. 

## Bug
The `bug.js` file shows an incorrect implementation where the `count` state is included in the `useEffect` dependency array. This will lead to an infinite loop because the `useEffect` function will re-run every time the `count` changes, and this re-run updates the `count` again, causing it to re-run again infinitely.

## Solution
The `bugSolution.js` file presents a corrected implementation.  The dependency array is empty (`[]`), which means the `useEffect` function will only run after the first render. This prevents infinite loops and ensures that the log is outputted only when the component mounts.