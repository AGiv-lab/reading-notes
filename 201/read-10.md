# 201-Reading_10

##Debugging

[What Went Wrong? Troubleshooting JavaScript](https://developer.mozilla.org/en-US/docs/Learn/JavaScript/First_steps/What_went_wrong){:target="_blank"}.

1. *Name some key differences between a **Syntax Error** and a **Logic Error**.*
**Syntax Error**Typeos missing brackets, mispelling or other user typing error **Logic error** -the code runs but the does the wrong thing, the output is wrong but the result works. wrong math, usuing a method that isnt recognized. The concept is right, but the result is wrong. Syntax stop code from running but logic errors run and produce the wrong result. 

2. *List a few types of errors that you have encountered in past lab assignments and explain how you were able to correct them*. Type-os in syntax or errors in typing seem to be the most common.. leaving an extra set of double brackets after i switched the code.


3. *How will this topic continue to influence your long term goals*? I'm able to do a cursory search to look for red indicators on vs code, and use the console to look for mistakes

[The JavaScript Debugger](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/What_are_browser_developer_tools#the_javascript_debugger){:target="_blank"}.

1. *How would you describe the JavaScript Debugger tool and how it works to someone just starting out in software development?*  Knowing where to start debugging, sources tab , click line number and insert break point then it inspects the variable line by line.

2. *Define what a breakpoint is*. Break point is a marker to pause executing at that point. Then inspect variables, check the call stack and inspect code line by line.  issues from there. find logic bugs you see what values different variables have. It helps understand how your program flows 

3. *What is the call stack?* The call stack is how js keeps track of calls. LIFO- (last in, first out) works like a stack of plates, used in arrays a lot
1-A function is called and is added to the stack. 
2-if it calls another function, that one goes on top
3-when the function finishs it is removed from the call stack (of plates)
4-executuion continues with the function below it 

helps trace errors when it happening , recursion issues , infinite loops 

## Bookmark and Review

[Debugging HTML](https://developer.mozilla.org/en-US/docs/Learn/HTML/Introduction_to_HTML/Debugging_HTML){:target="_blank"}

[Debugging CSS](https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Debugging_CSS){:target="_blank"}

## End of Class Review

1. *What are a few ways we can debug our code?* 

-The most common way is using console.log to print values to the console and check if your code is behaving as expected.

-You can also use the browser dev tools (F12) to inspect errors, set breakpoints, and step through your code line by line.

-The debugger keyword is another option which pauses execution at a specific line so you can examine what's happening at that point.


1. *What are some of the error types you may encounter in the console?*
## Common Console Error Types

1. **Syntax Error**
   - Occurs when JavaScript code has incorrect syntax.
   - Example: missing brackets, quotes, or parentheses.

2. **Reference Error**
   - Happens when trying to use a variable that has **not been declared**.

3. **Type Error**
   - Occurs when a value is **not of the expected type**.
   - Example: calling a method on `undefined` or `null`.

4. **Range Error**
   - Happens when a number is **outside the allowed range**.
   - Example: invalid array length.

5. **URI Error**
   - Occurs when using **incorrect URI encoding/decoding functions**.

6. **Eval Error**
   - Related to improper use of the `eval()` function (rare today).

### Major Browsers' Debugging Tools

**Keyboard**:

1. Windows: `ctrl` + `shift` + `i`

1. macOS: `command` + `option` + `i`

**Chrome**:

1. Open the browser.

1. From the menu, select "More Tools".

1. From tools, choose "Developer Tools".

1. Select Console.

**Firefox**:

1. Open the browser.

1. From the menu, select "Web Developer".

1. Select "Web Console".

**Safari**:

1. Go to Safari, Preferences, Advanced in the main menu.

1. Check "Enable Show Develop menu in menu bar".

1. From the Develop menu, select "Show Web Inspector".


### Major Browsers' Debugging Tools

**Keyboard**:

1. Windows: `ctrl` + `shift` + `i`

1. macOS: `command` + `option` + `i`

**Chrome**:

1. Open the browser.

1. From the menu, select "More Tools".

1. From tools, choose "Developer Tools".

1. Select Console.

**Firefox**:

1. Open the browser.

1. From the menu, select "Web Developer".

1. Select "Web Console".

**Safari**:

1. Go to Safari, Preferences, Advanced in the main menu.

1. Check "Enable Show Develop menu in menu bar".

1. From the Develop menu, select "Show Web Inspector".

###JAVASCRIPT

console.log(variableName);
-Check if variables contain the expected values

-See if code sections are running

-Track program flow
