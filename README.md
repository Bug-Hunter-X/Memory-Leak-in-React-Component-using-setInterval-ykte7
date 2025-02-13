# React setInterval Memory Leak
This example demonstrates a common mistake when using setInterval within a React component's useEffect hook: forgetting to clear the interval when the component unmounts. This leads to memory leaks and performance issues.

## Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks the cleanup function required to stop the interval when the component is unmounted.  This causes the interval to continue running even after the component is no longer needed, leading to a memory leak.

## Solution
The `bugSolution.js` file provides the corrected version. It uses the return value of `useEffect` to add a cleanup function that uses `clearInterval` to stop the interval before the component unmounts, resolving the memory leak.