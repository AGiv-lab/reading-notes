# 201-Reading_06

## **JavaScript Objects**

Object — a way to group related information together

Think of it like a profile card with labels and values

Explaining an Object (Non-Technical)

An object is like a backpack holding related items, each with a label

## **Advantages of Object Literals**

Easy to read and write

Keeps related data organized

Makes code easier to understand and maintain

## Objects vs Arrays

*Objects use named keys*

***Arrays use numbered indexes***

-Use *objects* when data describes something

Use ***arrays*** for ordered lists



## **Bracket vs Dot Notation**

Use bracket notation when:

-Property name has spaces

-Property name is stored in a variable

Example:

dog["favorite toy"]


Using this Keyword

const dog = {
    name: 'Spot',
      age: 2,
        color: 'white with black spots',
          humanAge: function (){
    console.log(`${this.name} is ${this.age * 7} in human years`);
  }
}


  *this refers to the current object (dog)*

-Advantage:

-Makes methods reusable

-Avoids hard-coding object names



## **The DOM (Document Object Model)**

***DOM — a representation of the HTML page as a tree of objects***

Allows JavaScript to:

-Read HTML

-Change content

-Respond to user actions


## ***DOM + JavaScript Relationship**

*JavaScript uses the DOM to interact with the webpage*

Without the DOM, JavaScript could not change the page content


## ***Problem Domain***

**Problem domain — understanding what you are solving before coding**

*Hardest part of programming is knowing the problem clearly*



## **Primitive Values vs Object References**

**Primitive values:**

*Stored by value*

Examples: string, number, boolean

***Object references:***

*Stored by reference*

Changes affect all references to the object