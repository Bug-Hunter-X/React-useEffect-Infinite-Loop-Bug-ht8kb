# React useEffect Infinite Loop Bug
This repository demonstrates a common bug in React's `useEffect` hook: an infinite loop caused by a missing dependency in the dependency array. 

The `bug.js` file contains the buggy code.  The `bugSolution.js` file provides the corrected code.

## Bug Description
The `useEffect` hook in `bug.js` is intended to log the current count to the console after each render. However, because `count` is not included in the dependency array, the effect runs after every render, causing an infinite loop and potentially crashing the browser.  This happens because the effect function itself is recreated each render causing it to fire regardless of changes to `count`.

## Solution
The solution in `bugSolution.js` adds `count` to the dependency array. Now the effect only runs when the `count` value changes.