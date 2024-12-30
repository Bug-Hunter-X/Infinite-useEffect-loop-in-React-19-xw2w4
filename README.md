# Infinite useEffect loop in React 19

This repository demonstrates a common error in React 19 where an infinite loop occurs due to an improperly used `useEffect` hook.  The `useEffect` hook, when defined without dependencies, runs after every render, leading to performance degradation and potential crashes.

## Problem

The provided `bug.js` file contains a `MyComponent` that uses `useEffect` without specifying a dependency array.  This causes the effect to run repeatedly, resulting in an infinite loop.

## Solution

The `bugSolution.js` file provides the corrected component.  Adding an empty dependency array `[]` to `useEffect` ensures that the effect only runs once after the initial render.  Alternatively, if the effect needs to run based on certain state changes, the relevant state variables should be included in the dependency array. 

## How to Reproduce

1. Clone this repository.
2. Navigate to the repository's directory in your terminal.
3. Run `npm install` to install the dependencies.
4. Run `npm start` to start the development server. Observe the console output, which shows the continuous execution of the effect in `bug.js`.
5. Compare the behavior with `bugSolution.js` to see the resolved issue.