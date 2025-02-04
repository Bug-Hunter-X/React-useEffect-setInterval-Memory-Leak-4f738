# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications involving the `useEffect` hook and `setInterval`.  The example shows how forgetting to return a cleanup function from `useEffect` when using `setInterval` leads to memory leaks and potentially unexpected component behavior.

The `bug.js` file contains the buggy code. The `bugSolution.js` file provides a corrected version with a proper cleanup function.

## How to Reproduce

1. Clone the repository.
2. Run `npm install` to install the necessary dependencies.
3. Run `npm start` to start the development server.
4. Observe the count rapidly increasing; this indicates the memory leak.
5. Switch to the corrected file to see the proper behavior.

## Solution

The solution involves adding a return statement within the `useEffect` cleanup function to clear the interval before the component unmounts or re-renders. This prevents the interval from continuing to run unnecessarily, thereby avoiding memory leaks.