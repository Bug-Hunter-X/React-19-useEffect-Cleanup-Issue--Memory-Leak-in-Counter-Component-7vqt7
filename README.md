# React 19 useEffect Cleanup Issue: Memory Leak
This repository demonstrates a common error in React 19's `useEffect` hook, leading to a memory leak.  The example shows an incorrect implementation where the return function (cleanup) within `useEffect` is not properly implemented.

## Problem
The `useEffect` hook in React allows for performing side effects. It's crucial to use the cleanup function (returned from `useEffect`) to remove any resources created within the effect (such as timers, subscriptions, or event listeners).  Failure to do so results in memory leaks, especially when components unmount or when state changes frequently.

## Solution
The solution involves properly implementing the cleanup function within `useEffect`. Ensure you are removing any references and canceling any ongoing processes within this cleanup phase.

## How to Reproduce
1. Clone this repository.
2. Run `npm install`.
3. Run `npm start`.
4. Observe the console logs to see the repeated execution of the effect without proper cleanup.

## How to fix
Review the `bugSolution.js` file for a corrected version demonstrating proper cleanup within the `useEffect` hook.