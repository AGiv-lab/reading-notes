# Class 3 Readings: Passing Functions as Props

## Reading

[React Docs - lists and keys](https://react.dev/learn#rendering-lists)){:target="_blank"}

1. What does .map() return?
*.map() returns a new array.*
2. If I want to loop through an array and display each value in JSX, how do I do that in React? 
*Use .map() inside JSX.    array.map(item => <p>{item}</p>)*

3. Each list item needs a unique ____*key*______.
4. What is the purpose of a key? *A key helps React identify which items changed, updated, or were removed.*

[The Spread Operator](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Spread_syntax){:target="_blank"}

1. What is the spread operator? *The spread operator (...) copies or expands arrays and objects.*

2. List 4 things that the spread operator can do.
Copy arrays
Copy objects
Combine arrays
Add items to arrays or objects

3. Give an example of using the spread operator to combine two arrays.
*const arr3 = [...arr1, ...arr2];*

4. Give an example of using the spread operator to add a new item to an array.
*const newArray = [...arr, "new item"];*

5. Give an example of using the spread operator to combine two objects into one.
*const newObj = { ...obj1, ...obj2 }; *

<!-- ## Additional Resources

PLACEHOLDER -->

## Videos

[How to Pass Functions Between Components](https://www.youtube.com/watch?v=n-6i_WGIOKE){:target="_blank"}

  1. In the video, what is the first step that the developer does to pass functions between components?
  *The developer first creates the function in the parent component.*

  2. In your own words, what does the `handleClick` function do? *the (handleClick) function runs when the user clicks a button or element. It usually updates state or performs an action.*

  3. How can you pass a method from a parent component into a child component?
  *You pass the method as a prop.*

*<Child handleClick={handleClick} />* 

  4. How does the child component invoke a method that was passed to it from a parent component?
  *The child calls the function using props.*

- props.handleClick()

## Bookmark and Review

- [React Tutorial through 'Declaring a Winner'](https://reactjs.org/tutorial/tutorial.html){:target="_blank"}
- [React Docs - Lifting State Up]([https://reactjs.org/docs/lifting-state-up.html](https://react.dev/learn/sharing-state-between-components#lifting-state-up-by-example){:target="_blank"}{:target="_blank"}