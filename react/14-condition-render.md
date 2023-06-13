# React Conditional Rendering

In React, you can conditionally render components.

There are several ways to do this.

if Statement
We can use the if JavaScript operator to decide which component to render.

Example:
We'll use these two components:

```js
function MissedGoal() {
  return <h1>MISSED!</h1>;
}

function MadeGoal() {
  return <h1>Goal!</h1>;
}
```
