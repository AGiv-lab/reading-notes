# 102-Reading_05

##Design Web Pages with CSS

*What is the purpose of **CSS**?*

###Cascading Style Sheets

**CSS helps style elements of the HTML structure. It is a styling tool used to assist in creating web pages. It is a visual assistant aimed towards consistent results in web design rendering. Html is the structure, where CSS is the design**

*What are the three ways to insert CSS into your project?*

-Inline
-Internal 
-External

+Inline **example** 
*<p style="color: blue; font-size: 16px;">Hello World</p>*

+**Internal example**
 *<head>
  <style>
    p {
      color: blue;
      font-size: 16px;
    }
  </style>
</head>*

+**External example**
*<head>
  <link rel="stylesheet" href="styles.css">
</head>*

####Write an example of a CSS rule that would give all <p> elements red text.

p {
    color: red;
}