# React Native: Accessing State Before Mount

This repository demonstrates a common error in React Native: attempting to access component state or props before the component has fully mounted.  This often results in undefined values and unexpected behavior.

## Problem
The `bug.js` file shows a component that attempts to fetch data and set state in the constructor.  Because `fetchData()` is asynchronous, the state might not be populated by the time the render method executes.  This leads to `this.state.data` being undefined, causing a potential error.

## Solution
The `bugSolution.js` file provides a solution by using the `componentDidMount()` lifecycle method.  This method ensures that the data is fetched and state is updated *after* the component has successfully mounted. This prevents the error of accessing state or props before they are defined.