# Reading: Stacks and Queues

## Stack

A **stack** is a data structure made of nodes where items are added and removed from the **top**.

Stacks follow **LIFO (Last In, First Out)** — the last item added is the first item removed.

### Stack Methods

- `push()` — adds an item to the top
- `pop()` — removes and returns the top item
- `peek()` — views the top item without removing it
- `isEmpty()` — checks whether the stack is empty

These operations are **O(1)** because they work directly with the top of the stack.

### Stack Analogy

A stack is like a stack of plates. You add a plate to the top and remove a plate from the top.

---

## Queue

A **queue** is a data structure where items enter at the **rear** and leave from the **front**.

Queues follow **FIFO (First In, First Out)** — the first item added is the first item removed.

### Queue Methods

- `enqueue()` — adds an item to the rear
- `dequeue()` — removes and returns the front item
- `peek()` — views the front item without removing it
- `isEmpty()` — checks whether the queue is empty

These operations are also **O(1)**.

### Queue Analogy

A queue is like standing in line. The first person to enter the line is the first person served.

---

## Key Difference

**Stack:** Last In → First Out (**LIFO**)  
**Queue:** First In → First Out (**FIFO**)

## What I Learned

The main thing I learned is that stacks and queues organize data differently. A stack works from one end, while a queue adds items at the rear and removes them from the front. Both can perform their main operations in constant **O(1)** time.