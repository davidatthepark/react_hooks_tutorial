# react_hooks_tutorial

https://reactjs.org/docs/hooks-intro.html

## What are Hooks?
- Hooks are functions that let you "hook into" React state and lifecycle features from function components.

## useState
- `useState` is a hook in which you can add state.

## useEffct
- `useEffect` adds the ability to perform side effects from a function component. It serves the same purpose as `componentDidMount`, `componentDidUpdate`, and `componentWillUnmount` but unified into a single API.
- Defined inside a component so it has access to props and state.
- By default, runs after every render -- including the first render.
- Effects may also specify how to "clean up" after them by returning a function. Subscribe/unsubscribe.
- Hooks let you organize side effects in a component by what pieces are related, rather than forcing a split based on lifecycle methods.
- Unlike `componentDidMount` and `componentDidUpdate`, effects scheduled with `useEffect` don't block the browser from updating the screen. This makes your app feel more responsive. The majority of effects don't need to happen synchronously. In the uncommon cases where they do (such as measuring the layout), there is a separate `useLayoutEffect` Hook with an API identical to `useEffect`.
- Previously, we could avoid memory leaks by using `componentWillUnmount`. Now, we can return a function from `useEffect`.
- `useEffect` will be different on every render. The cleanup will also be run on every render. This lets us avoid having to unsubscribe on `componentDidUpdate`. It is cleaned up by default. If performance becomes an actual issue, you can skip it by passing an array as an optional second argument to `useEffect`.
- Important optimization notes: https://reactjs.org/docs/hooks-effect.html#tip-optimizing-performance-by-skipping-effects

## Rules of Hooks
- Hooks are functions, but they impose two additional rules:
    - Only call Hooks at the top level. Don't call Hooks inside loops, conditions, or nested functions.
    - Only call Hooks from React function components.

## Custom Hooks
- You can create your own hooks. The benefit here is reusing stateful behavior between different components. It might let you avoid using HOCs or render props.
