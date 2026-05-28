# Class 4 Readings: React and Forms

## Reading

[How to use Forms in React](https://www.robinwieruch.de/react-form/){:target="_blank"}

  1. What is a 'Controlled Component'?
  
  *A controlled component is a form element, like an input, that is controlled by React state.*

This means the input’s value comes from state, and when the user types, React updates the state.

  2. Should we wait to store the users responses from the form into state when they submit the form OR should we update the state with their responses as soon as they enter them? 
  *We should update the state as soon as the user enters their responses.*
**Why**.
This keeps React in control of the form data. It also makes it easier to validate input, show live updates, and use the form data before the user submits.
  3. How do we target what the user is entering if we have an event handler on an input field?
  *We use the event object and target the input’s value with:*

event.target.value

Example:

function handleChange(event) {
  setName(event.target.value);
}

[The Conditional (Ternary) Operator Explained](https://codeburst.io/javascript-the-conditional-ternary-operator-explained-cac7218beeff){:target="_blank"}

  4. Why would we use a ternary operator?
  *We use a ternary operator as a shorter way to write simple if...else statements.*

*It makes code cleaner and easier to read when choosing between two values or actions.*
-Syntax
condition ? valueIfTrue : valueIfFalse;
Example
let message = isLoggedIn ? "Welcome back!" : "Please log in";

This means:

If isLoggedIn is true → "Welcome back!"
Otherwise → "Please log in"

  5. Rewrite the following statement using a ternary statement:

     ```javascript
     if(x===y){
       console.log(true);
     } else {
       console.log(false);
     }
     ```
     *x === y ? console.log(true) : console.log(false);*

## Bookmark and Review

- [React Bootstrap - Forms](https://react-bootstrap.github.io/docs/forms/overview){:target="_blank"}
- [React Docs - conditional rendering](https://react.dev/learn/conditional-rendering){:target="_blank"}