# 201-Reading_07

# Domain Modeling

## Why do we need domain modeling?
Domain modeling is the process of representing real-world concepts as code. It helps developers identify the objects, properties, and behaviors needed to solve a problem before writing code. Domain modeling improves code organization, reduces complexity, and makes applications easier to maintain and scale. By planning structure first, developers avoid duplicated logic and unclear relationships between data.

---

# HTML Tables

## Why should tables not be used for page layouts?
Tables should not be used for page layouts because they are designed specifically for displaying tabular data, not structuring a webpage. Using tables for layout breaks semantic meaning, creates accessibility issues for screen readers, makes responsive design difficult, and results in code that is harder to maintain. Modern layouts should be built using CSS tools like Flexbox or Grid.

## List and describe 3 semantic HTML elements used in an HTML `<table>`

1. **`<table>`**  
   Defines the table and tells the browser that the content is tabular data.

2. **`<th>` (Table Header)**  
   Represents header cells and provides labels for table data. Screen readers use these headers to explain relationships between data cells.

3. **`<td>` (Table Data)**  
   Contains the actual data within the table and is associated with header cells for accessibility.

---

# Constructors (JavaScript)

## What is a constructor and what are some advantages to using it?
A constructor is a special function used to create multiple objects with the same structure and behavior. Constructors act as blueprints for objects. Advantages include reduced code repetition, consistent object creation, better organization, and the ability to use prototypes for shared methods, which improves performance.

## How does the term `this` differ when used in an object literal versus when used in a constructor?
In an object literal, `this` refers to the object itself and always points to that specific object. In a constructor, `this` refers to the new object being created when the constructor is called with the `new` keyword. Each instance created by the constructor has its own `this` reference.

---

# Object Prototypes and Inheritance

## Explain prototypes and inheritance using an analogy from previous work experience
Prototypes and inheritance can be compared to a shared workplace handbook. When a new employee is hired, they do not receive a completely new copy of company rules written just for them. Instead, all employees reference the same handbook. In JavaScript, the constructor creates new objects (employees), while the prototype acts like the shared handbook that stores common methods. Inheritance allows each object to access shared behavior without duplicating it, saving memory and keeping behavior consistent.

---

# HTML Tables: Advanced Features and Accessibility (Review)

When using tables, accessibility should be a priority. Best practices include using `<caption>` to describe the table’s purpose, `<thead>`, `<tbody>`, and `<tfoot>` to group content, and `<th>` elements with proper `scope` attributes to define relationships between headers and data cells. Tables should only be used for data, not layout, to ensure screen readers can interpret them correctly.