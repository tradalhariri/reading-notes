# React Docs - thinking in React

## How would you break a mock into a component heirarchy?
We need to draw boxes on  every component and subcomponent in the mock design and think that every component should be responible on only one job. Because any component may be grow and be complex we need to divide large component into sub small components .
## What is the single responsibility principle and how does it apply to components?
single responsibility principle is a technique that any component should do only and one job. 
## What does it mean to build a ‘static’ version of your application?
There is no interactivity in the static version and there is no changes that may happen to the static app data.
## Once you have a static application, what do you need to add?
we need to start thinking how making it interactive and which components should render something depending on state. we need to find the common parent component to update the state inside it.

## What are the three questions you can ask to determine if something is state?
* `Is it passed in from a parent via props? If so, it probably isn’t state.`
* `Does it remain unchanged over time? If so, it probably isn’t state.`
* `Can you compute it based on any other state or props in your component? If so, it isn’t state.`

## How can you identify where state needs to live?

we need to identify each component that renders depending on changes in the state.when we identify all these components we need to identify the common parent component and this component can own the state.

## Things I want to know more about

I want to know more about conditional rendering in React.


## References 
[React Docs - thinking in React](https://reactjs.org/docs/thinking-in-react.html)

