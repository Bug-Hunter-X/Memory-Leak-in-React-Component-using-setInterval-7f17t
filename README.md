# React setInterval Memory Leak
This repository demonstrates a common mistake in React: using setInterval within useEffect without proper cleanup.  This can lead to memory leaks and performance issues.

## The Bug
The `bug.js` file contains a React component that uses `setInterval` to update a counter every second. However, it lacks the necessary cleanup function within the `useEffect` hook to stop the interval when the component unmounts. This results in the interval continuing to run even after the component is removed from the DOM, leading to a memory leak.

## The Solution
The `bugSolution.js` file provides a corrected version of the component.  It includes a cleanup function that uses `clearInterval` to stop the interval when the component unmounts, preventing the memory leak.

## How to reproduce
1. Clone the repository
2. Run `npm install`
3. Run `npm start`
4. Observe the counter increasing.  Note that even after navigating away from the component, the counter continues to increment in the background. This shows the memory leak from the uncleaned interval.

## How to fix
Always clean up intervals, timeouts, and other resources within the cleanup function of `useEffect`. This ensures that memory leaks are avoided.