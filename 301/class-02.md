# React: Component Lifecycle Events

## Based off the diagram, what happens first, the ‘render’ or the ‘componentDidMount’?

The `render` happens before the `componentDidMount` and the `componentDidMount` invoked immediatly after the component mounted.

## What is the very first thing to happen in the lifecycle of React?

the very first thing to happen in the lifecycle of React is the constructor invokation and it will be invoked before the component is mounted. 

## Put the following things in the order that they happen: componentDidMount, render, constructor, componentWillUnmount, React Updates

- constructor
- render
- componentDidMount
- React Updates
- componentWillUnmount

## What does componentDidMount do?
 
 `componentDidMount` will ensure that the component is rendered successfully and this is the right time and the right place where we can fetch data from the internet.


 ![React life cycle](https://miro.medium.com/max/2000/0*0saPKFiTUk6W3FYp)

# React State Vs Props

## What types of things can you pass in the props?
we can pass in the props the things that the component would inintialize with them or the things how  the component  would look like with them.
## What is the big difference between props and state?

the big difference between props and state is that the props are passed to the component and are handled out side of it where as the state is handled inside the component.
## When do we re-render our application?
when our application change its state.  for example when a user do somthing like he checked a box on the form or somthing like this we need to store that state and rerendered our app to change its state.
## What are some examples of things that we could store in state?

- checked a checkbox on the fome.
- increment a counter by clicking button.


## Things I want to know more about

I do not understand correctly where we can use some component life cycle methods .Like these :

* UNSAFE_componentWillMount()
* UNSAFE_componentWillUpdate()
* UNSAFE_componentWillReceiveProps()

## References 
[React: Component Lifecycle Events](https://medium.com/@joshuablankenshipnola/react-component-lifecycle-events-cb77e670a093)


[React State Vs Props](https://www.youtube.com/watch?v=IYvD9oBCuJI)