# React useEffect Cleanup: Forgetting to clear intervals

This example demonstrates a common mistake in React's `useEffect` hook: forgetting to clear intervals or timeouts in the cleanup function.  This can lead to memory leaks and unexpected behavior.

The `bug.js` file shows the problematic code, and `bugSolution.js` provides the corrected version.

## Problem

The `setInterval` function starts a timer that repeatedly updates the component's state. However, without a cleanup function to clear the interval when the component unmounts, the interval continues to run indefinitely, potentially causing a memory leak.

## Solution

The solution involves returning a cleanup function from the `useEffect` hook. This function should use `clearInterval` to stop the interval when the component unmounts or when the dependencies change.