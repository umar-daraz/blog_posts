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
Purpose of State is to update the component (and its children) UI with dynamic data that can change over time.

E.g. of state are




