# 201-Reading_09

## Reading 9

### [HTML Forms](https://developer.mozilla.org/en-US/docs/Learn/Forms){:target="_blank"}

[Your first Web Form](https://developer.mozilla.org/en-US/docs/Learn/Forms/Your_first_form){:target="_blank"}.
[How To Structure A Web Form](https://developer.mozilla.org/en-US/docs/Learn/Forms/How_to_structure_a_web_form){:target="_blank"}.

***Reading 9 Questions***

 *Why are forms so important in web development?*
 Keep it simple and only ask for what's needed 
 Use clear labels and placeholder text
Show helpful error messages

 *How would you describe events to a non-technical friend?*
 An event is just the browser noticing something happened — like a click or a keypress — and reacting to it.

 *When using the `addEventListener()` method, what 2 arguments will you need to provide?*
 Describe the event object. Why is the target within the event object useful?
What is the difference between event bubbling and event capturing?

5. *List 5 form elements and explain their importance.* 
Five form elements:

<input> — collects text, passwords, emails etc.
<textarea> — for longer text responses
<select> — a dropdown list of options
<button> — submits or triggers an action
<checkbox> — lets users select multiple options

### [Learn JS](https://developer.mozilla.org/en-US/docs/Learn/JavaScript){:target="_blank"}

[Introduction To Events](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/Building_blocks/Events){:target="_blank"}.


## Bookmark and Review

[HTML5 Input Types](https://developer.mozilla.org/en-US/docs/Learn/Forms/HTML5_input_types){:target="_blank"}

[Event Reference and listings](https://developer.mozilla.org/en-US/docs/Web/Events){:target="_blank"}


## End of Class Review

1. *What is a JavaScript Event?*
A JavaScript event is an action that happens in the browser, such as a user clicking a button, typing in a field, or submitting a form. JavaScript can "listen" for these events and respond to them.

2.*What 2 arguments do we need to pass into the `addEventListener()` method for it to run correctly?*The event type — a string like "click", "submit", "keydown"
The callback function — the function to run when the event fires

3. *What is a callback function?* A callback function is a function passed as an argument into another function, to be executed later. In events, it runs when the event is triggered.

4. *An HTML form is used to collect `________` input.* An HTML form is used to collect **user** input.

5. *An `<input>` element can be displayed in many ways, depending on the `_______`* attribute.
An <input> element can be displayed in many ways, depending on the **type attribute** — for example type="text", type="password", type="checkbox".

6. *What does `event.preventDefault()` do?*
It prevents the browser's default behavior from occurring. For example, stopping a form from refreshing the page on submit:


### Form Steps

1. build form in HTML

2. Grad form using JS

3. add submit listener

4. Prevent default behavior

5. Get input valuses

6. Create elements

7. Append to the DOM

8. Update or count elements