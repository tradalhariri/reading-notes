# Component-Based Architecture

## What is a component?
a component is a well defined encapsulated functionalty .we can reuse or replace it through the app as well as a component can interact with other components.

## What are the charactistics of a component?
* Reusability : we can reuse components throughout the app or other apps.

* Replaceable : we can replace components by other similar components.

* Not context specific : components dose not have a specific context or enviroment to work in. It is designed to work in different environments and contexts.
 
* Extensible : we can extends a component by add other components to it to make a new behaviour.

* Encapsulated : when we use  a component we do not need to see its detailes or how it was implemented. it encapsulate all variables ,state and functionality inside it.

* Independent : a component is designed to be independentless from other components.

## What are the advantages of using component based architecture?


- Ease of deployment : we can replace older version without impact on the other components.

- Reduced cost : you can reduce the cost of deployment and maintenance by using third part components.

- Ease of development : there is no impact on the development process through using components as they implement well-known interfaces to provide defined functionality.

- Reusable : we can reuse components across several apps or systems.

- Modification of technical complexity : `a component modifies the complexity through the use of a component container and its services.`

 

- Reliability : when we reuse a component the reliability of all system  enhances since a component is reliable.

- System maintenance and evolution : it is easy to change or modify the system since we changes only the components.

- Independent : the speed of the development process increases since the team can work in parallel on independent components.



# What is “Props” and how to use it in React?

## What is props short for?
props is stands for properties and used to passing data between components.props are being passed  between components in uni-directional flow(one way from parent to child).

## How are props used in React?

we can pass props as arguments to the child component from its parent. the following example explaines how we passed dynamically data from ParentComponent to the ChildComponent using props. we can add another child component with different text property value through using the props.

```javascript
class ParentComponent extends Component {  
  render() {
    return (
      <h1>
        I'm the parent component.
        <ChildComponent text={"I'm the 1st child"} />
        <ChildComponent text={"I'm the 2nd child"} />
        <ChildComponent text={"I'm the 3rd child"} />
      </h1>
    );
  }
}


const ChildComponent = (props) => {  
  return <p>{props.text}</p>; 
};
```
![props](https://miro.medium.com/max/3000/1*Kd52H-jKv6N1Cwgnaz4tOA.png)

## What is the flow of props?
the data flows in uni-direction flow from parent to its children and it is read-only.

## Things I want to know more about
I do not understand exactly what the following sentence means:

`Modification of technical complexity : a component modifies the complexity through the use of a component container and its services.`

## References 
[Component-Based Architecture](https://www.tutorialspoint.com/software_architecture_design/component_based_architecture.htm)

[What is “Props” and how to use it in React?](https://itnext.io/what-is-props-and-how-to-use-it-in-react-da307f500da0)

[Example of React Props](https://youtu.be/KvapOdsFK5A)