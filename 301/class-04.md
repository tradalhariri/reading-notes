# React Docs - Forms

## What is a ‘Controlled Component’?
The HTML form elements such as `input select textarae` save their own internal state.in React we save the state in `state` property and control it by calling `setState` methode. we can combine both by making React is source of truth. React component can render the form and  control its input changes then we can call any form input element whose value is controled by React component a `controled component`.
## Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? Why.

No we should update the state with their responses as soon as the user enter them.by this way we can pass values to other UI element or rest them by other event handler. 
## How do we target what the user is entering if we have an event handler on an input field?
By storing the value of input in the state and update the state using `setState` inside the event handler depending on what the `event.target.value` is .

# The Conditional (Ternary) Operator Explained

## Why would we use a ternary operator?

It is a shorter way than using `else if statements`;
## Rewrite the following statement using a ternary statement:
```javascript
 if(x===y){
 console.log(true);
  } else {
 console.log(false);
  }
```

```javascript
x === y ?  console.log(true):console.log(false);
```

## Things I want to know more about

I wnat to know more about ES6 features and practice them.


## References 
[React Docs - Forms](https://reactjs.org/docs/forms.html)

[The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff)
