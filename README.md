# React useEffect Hook Memory Leak

This repository demonstrates a common React coding error: forgetting the cleanup function in a `useEffect` hook.  This can lead to memory leaks if not handled correctly.  The `bug.js` file shows the flawed code, while `bugSolution.js` provides the corrected version.

## Description

The issue lies within the `useEffect` hook of the `MyComponent` component. The `useEffect` hook runs side effects, and, it is important to provide a return function to cleanup any side effects done inside the function, which is usually associated with subscription, timer, or event listener.   The provided example omits the return statement.  Without a cleanup function, the `console.log` will continue to execute when the component unmounts, leading to unnecessary actions and potential memory leaks, especially if the component is repeatedly mounted and unmounted.

## Solution

The corrected code includes a return function within the `useEffect` hook. This ensures that any unnecessary actions are cleaned up before the component is unmounted, effectively preventing memory leaks.  The solution file shows the correct implementation.