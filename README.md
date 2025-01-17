# React useEffect Infinite Loop Bug

This repository demonstrates a common bug in React applications involving the `useEffect` hook.  The bug is caused by omitting the dependency array in `useEffect`, leading to an infinite render loop.

## The Problem
The provided `MyComponent` uses the `useEffect` hook without a dependency array. This means that the effect runs after every render, causing a continuous loop because updating the `count` within the `onClick` handler triggers a re-render, which in turn triggers the effect again, and so on.

## The Solution
The solution involves adding a dependency array to the `useEffect` hook. In this case, we add `[count]` as the dependency array, ensuring that the effect only runs when the `count` variable changes.