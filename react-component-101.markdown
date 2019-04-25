---
Title: React Component 101
author: Umar
---

## Props
Props are like parameters of a function. We use these to make our component dynamic like we use parameters to make our function dynamic.

lets look at a component to display Greetings to Harry Poter. 

```
const GreetingHarryPoter = () => (
    <span>Hello Harry Poter</span>
)
```
Now I want to say greeting to any person not just Harry Potter, I can refactor my component to take in a prop i.e the name of person. And rename my component to more generic name because now I can use this component to say greeting to anybody.

```
const Greeting = ({name}) => (
    <span>Hello {name}</span>
)
```
And Now I can say greeting to different persons like
```
const App = () => (
    <Greeting name="Harry Potter">
    <Greeting name="Hermione Granger">
    <Greeting name="Ron Weasley">
)
```

## State
Anything that happen in React App we capture this by changing State.
Like
- User Clicks A button we do change state.
- Network returns data we do change state.
- Anything else happen we change state.

Lets consider a simple example of counter that we can increment or decrement.

Lets create a component without state.
```
const Counter = () => {
  return (
    <div>
      <button>-</button>1<button>+</button>
    </div>
  );
};
```
We have set the initial counter value to 1.
But as you click on increment or decrement we want to change the counter value. 
To make counter dynamic we have to initial it with useState hook

```
const Counter = () => {
  const [count, setCount] = useState(1);
  return (
    <div>
      <button>-</button>
      {count}
      <button>+</button>
    </div>
  );
};
```
we call useState with initial value (i.e 1) and it returns us the value(count) and a function (setCount) to change the value in future.

Now we have a function that we can call whenever you click on increment(-) or decrement(+) buttons to set new value.
```
const Counter = () => {
  const [count, setCount] = useState(1);
  const increment = () => setCount(count + 1);
  const decrement = () => setCount(count - 1);
  return (
    <div>
      <button onClick={decrement}>-</button>
      {count}
      <button onClick={increment}>+</button>
    </div>
  );
}
```

### Summary

At the simplest level we can consider props as parameters to a function.
And we can consider state as React way to update User Interface.