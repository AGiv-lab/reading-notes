# 201-Reading_08

### Learn CSS -Flexbox

1. **Flexbox** is designed for one-dimensional content, meaning 1D is best for components and layouts are best for 2D  (the grid)
Flexbox:

Distributes space along one axis

Aligns items relative to that axis

Does not control both rows and columns together

Even when items wrap, Flexbox is still:

controlling one row (or one column) at a time

2.**Explain the difference between main axis and cross axis-** justify main align cross
Main Axis (primary direction)

The main axis is the direction Flexbox uses to place items.
Cross Axis (secondary direction)

The cross axis always runs perpendicular to the main axis.

You don’t set it directly.
It changes automatically when the main axis changes.
How alignment works on each axis
Main-axis alignment → justify-content
justify-content: center;

Moves items along the main axis

Cross-axis alignment → align-items
align-items: center;

Moves items along the cross axis

CSS
.container {
  display: flex;
  justify-content: center;
  align-items: center;

justify-content → left/right

align-items → up/down

3. How can the screen readers reader content not
tab isnt going to select items based on flow.  It goes in order. Structure html first and layour second.
use flexbox for layout (not poor html structure)
*row reverse*
*order-* if you use that, when the html is not the same , it causes probs It could be confusing for user or screen readers.

**Flexbox**
*What are some advantages of using this for long term goals. - it is used in modern web dev* It helps to build a foundation for CSS grid and helps write industry standard CSS . Software ENG- you must understand flexbox.

Flexbox was designed specifically for layout. Better justify content and align items, cross axis. More responsive than float by default. 

***Float***

**Float** was designed to wrap text around images, not to build layouts. float is a bandaid, a workaround . Flexbox is the solution.

#### Additional Flashcard for Study 

##### Flashcard 1

Q: What is Flexbox designed for?
A: One-dimensional (1D) layouts — either rows or columns, but not both at the same time.

Flashcard 2

Q: What does Flexbox control?
A: Space distribution and alignment along a single axis.

Flashcard 3

Q: When should CSS Grid be used instead of Flexbox?
A: When controlling both rows and columns (2D layouts).

Flashcard 4

Q: What is the main axis in Flexbox?
A: The primary direction items are laid out, defined by flex-direction.

Flashcard 5

Q: What is the cross axis in Flexbox?
A: The axis perpendicular to the main axis; it changes automatically when the main axis changes.

Flashcard 6

Q: Which property aligns items on the main axis?
A: justify-content

Flashcard 7

Q: Which property aligns items on the cross axis?
A: align-items

Flashcard 8

Q: In a row direction, what does justify-content control?
A: Left-to-right alignment.

Flashcard 9

Q: In a row direction, what does align-items control?
A: Up-and-down (vertical) alignment.

Flashcard 10

Q: What happens to axes when flex-direction: column is used?
A:

Main axis becomes vertical

Cross axis becomes horizontal

Flashcard 11

Q: How do screen readers read content in a Flexbox layout?
A: In the order of the HTML, not the visual layout.

Flashcard 12

Q: Why can order and row-reverse cause accessibility problems?
A: They change visual order without changing HTML order, confusing screen readers and keyboard users.

Flashcard 13

Q: Best practice for accessible Flexbox layouts?
A: Structure HTML logically first, then apply Flexbox for layout.

Flashcard 14

Q: Why is Flexbox important for long-term web development skills?
A: It’s industry-standard, responsive, and foundational for learning CSS Grid.

Flashcard 15

Q: What was float originally designed for?
A: Wrapping text around images.

Flashcard 16

Q: Why is float not recommended for layouts?
A: It’s a workaround, hard to maintain, and not meant for layout.

Flashcard 17

Q: One sentence summary of Flexbox vs Float?
A: Float is a band-aid; Flexbox is the solution.

Flashcard 18

Q: What Flexbox properties are most commonly used for alignment?
A: justify-content and align-items

Flashcard 19

Q: What makes Flexbox more responsive than floats?
A: Built-in flexibility, auto spacing, and alignment without hacks.

Flashcard 20

Q: What is the biggest Flexbox mindset to remember?
A: Think in axes, not directions like left/right or up/down.