# Stale Closure in React's useEffect Hook with setInterval
This example demonstrates a common mistake when using the `setInterval` function within React's `useEffect` hook.  The problem lies in the creation of a stale closure, leading to unexpected behavior. 

## Problem
The provided `MyComponent` uses `setInterval` to update a state variable (`count`) every second. However, because the `count` variable within the `setInterval` callback is referencing its value at the time of the `useEffect` execution and not its current value, it will always use the initial count of 0.  The `setInterval` callback function does not refer to the latest value of the state variable.   This results in `count` never updating past 1.

## Solution
To resolve this, you must pass the updated `count` value to the `setCount` function with the callback version of `setCount` like demonstrated in the solution file.  This ensures that the latest value is always used when updating the state.