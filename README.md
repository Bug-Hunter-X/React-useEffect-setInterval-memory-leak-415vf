# React useEffect setInterval Memory Leak

This repository demonstrates a common error in React applications: memory leaks caused by the improper use of `setInterval` within the `useEffect` hook.

## The Problem

The `bug.js` file shows a component that uses `setInterval` to update a counter every second. However, it fails to include a cleanup function to stop the interval when the component unmounts.  This leads to a memory leak, as the interval continues to run even after the component is removed from the DOM.

## The Solution

The `bugSolution.js` file presents the corrected code.  It utilizes the return value of `useEffect` to implement a cleanup function that stops the interval using `clearInterval` when the component is unmounted. This prevents the memory leak.

## How to Reproduce

1. Clone this repository.
2. Run `npm install` to install the dependencies.
3. Run `npm start` to start the development server.
4. Observe the behavior of both `bug.js` and `bugSolution.js` components to understand the difference.

## Key Learning

Always include a cleanup function in `useEffect` when using timers or other resources that need to be released to prevent memory leaks. The cleanup function is executed before the component is unmounted.