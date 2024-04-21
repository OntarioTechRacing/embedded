# Data Structures and Algorithms

---

<details markdown="1">
  <summary>Table of Contents</summary>

-

</details>

---

## Intro to Algorithms

---

## Big O Notation

---

## Intro to Data Structures

Data structures are specialized formats for organizing, processing, managing, and storing data. They are critical for creating efficient software and algorithms.

### Key Data Structures

<ul>
  <li>Arrays: Simple lists of elements, accessible by indices.</li>
  <li>Linked Lists: Elements linked with pointers, allowing easy insertion and deletion.</li>
  <li>Stacks: Last-In, First-Out (LIFO) data structure.</li>
  <li>Queues: First-In, First-Out (FIFO) data structure.</li>
  <li>Hash Tables: Key-value pairs for efficient data lookup.</li>
  <li>Trees: Hierarchical structures, such as binary search trees.</li>
  <li>Graphs: Sets of nodes connected by edges, useful in modeling networks.</li>
<ul>

## Arrays

Arrays are the simplest and most widely used data structures. They consist of elements stored at contiguous memory locations. Each element can be accessed directly via its index, which makes array operations fast.

Some characteristics include:

<li>The size of the array is fixed size.</li>
<li>All elements in the array must be fixed size.</li>

```

# Creating an array of integers
integers = [10, 20, 30, 40, 50]

# Accessing the third element
print(integers[2])  # Output: 30 (Since python indexing starts at 0)

```

## Linked List

Linked Lists are a collection of nodes that together represent a sequence. Each node contains data and a reference (or link) to the next node in the sequence. This structure allows for efficient insertion and deletion.

Some characteristics include:

<li>The linked list depends on grow and shrink in size dynamically.</li>

```

class Node:
    def __init__(self, data):
        self.data = data
        self.next = None

# Creating a simple linked list with 3 elements
head = Node(1)
head.next = Node(2)
head.next.next = Node(3)

```

## Stacks

A stack is a collection of elements, with two main principal operations: push, which adds to the collection, and pop, which removes the most recently added element that was not yet removed. The last element added is the first one to be removed, hence the LIFO (Last In First Out) behavior.

Some characteristics include:

<li>It follws LIFO (Last In First Out) principle.</li>

```

stack = []
# Push elements
stack.append('a')
stack.append('b')
stack.append('c')

# Pop elements
print(stack.pop())  # Output: c
print(stack.pop())  # Output: b

```

## Queues

Queues are similar to stacks but operate in a FIFO (First In First Out) manner. Elements are added at the back and removed from the front.

Some characteristics include :

<li>IT follows FIFO (First In First Out) principle. </li>

```

from collections import deque

queue = deque()

# Enqueue elements
queue.append('1')
queue.append('2')
queue.append('c')

# Dequeue elements
print(queue.pop())  # Output: 1

```

## Hash Table

Hash tables store data in an associative manner. Data is stored in an array format, where each data value has its own unique index value. Access of data becomes very fast if we know the index of the desired data.

```

# Creating a hash table in Python using dictionary
my_hash_table = {'name': 'John Doe', 'age': 29, 'email': 'john@example.com'}

# Accessing data
print(my_hash_table['name'])  # Output: John

```

## Trees

Trees are hierarchical data structures with a root value and subtrees of children with a parent node, represented as a set of linked nodes.

---
