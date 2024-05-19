# Data Structures and Algorithms

---

<details markdown="1">
  <summary>Table of Contents</summary>

-

</details>

---

## Intro to Algorithms

Put simply, an algorithm is a set of instructions used to solve a certain task.
A good algorithm has the capability to accept input and aims to be well-ordered
and feasible.

---

### Sorting Algorithms

#### Binary Search

Binary Search is a searching algorithm used in a sorted array. It repeatedly
divides the search interval in half, narrowing down the possible location to
one. This method leverages the sorted nature of the array to achieve a time
complexity of $O \left( \log n \right)$.

**Binary search algorithm steps:**

1. Divide the search space into two halves by finding the middle index.
2. Compare the middle element with the key:
    - If the middle element is the key, the search terminates successfully.
    - If the middle element is larger than the key, use the left half for the
      next search.
    - If the middle element is smaller than the key, use the right half for the
      next search.
3. Repeat the process until the key is found or the search space is exhausted.

#### Linear Search

Linear Search is a sequential search algorithm that examines each element of the
list until the target element is found or the list ends. The average time
complexity is $O \left( n \right)$.

**Linear search algorithm steps:**

1. Treat each element as a possible match and examine it.
2. If an element matches the key, return the index of that element.
3. If no match is found by the end of the list, return "No match found".

#### Bubble Sort

Bubble Sort is a simple sorting algorithm that repeatedly swaps adjacent
elements if they are in the wrong order, making it less efficient for large
datasets due to its $O \left( n^2 \right)$ time complexity.

**Bubble sort algorithm steps:**

1. Start at the left, compare adjacent elements, and swap if necessary to move
   the larger element to the right.
2. Repeat the process for the next largest element until the data is sorted.

#### Insertion Sort

Insertion Sort builds a sorted sequence from an unsorted list by placing each
element into its correct position. It preserves the order of equal elements,
with a typical time complexity of $O \left( n^2 \right)$.

**Insertion sort algorithm steps:**

1. Consider the second element of the array as sorted.
2. Compare it with previous elements and swap if necessary.
3. Continue for each element until the array is sorted.

#### Selection Sort

Selection Sort improves efficiency by systematically selecting the smallest
element from the unsorted segment and moving it to the start. This process
repeats with the remaining unsorted section until the array is sorted, with a
time complexity of $O \left( n^2 \right)$.

**Selection sort algorithm steps:**

1. Divide the array into sorted and unsorted segments.
2. Find and swap the smallest element from the unsorted segment with the first
   unsorted element.
3. Repeat until the array is sorted.

#### Heap Sort

Heap Sort utilizes a Binary Heap structure, beginning by converting the list
into a heap, then repeatedly removing the largest element and maintaining heap
properties. It has a time complexity of $O \left( n \log n \right)$.

**Heap sort algorithm steps:**

1. Convert the array into a heap using the heapify process.
2. Swap the root of the heap with the last element and remove the last element.
3. Re-heapify the heap and repeat until one element remains.

---

### Divide and Conquer Algorithms

#### Quick Sort

Quick Sort uses a divide-and-conquer strategy to sort an array by selecting a
pivot and partitioning the surrounding array. It achieves this through recursive
partitioning.

**Quick sort algorithm steps:**

1. Select a pivot and partition the array around the pivot.
2. Recursively apply the same logic to the left and right partitions.
3. Continue until the array is sorted.

#### Merge Sort

Merge Sort divides the array into smaller segments, sorts them, and merges them
back into a sorted array. It's a recursive process that ensures stability in
sorting.

**Merge sort algorithm steps:**

1. Divide the array into two halves until it cannot be divided further.
2. Sort each half and merge them back into a single sorted array.
3. Repeat until the entire array is sorted.

---

### Graph Algorithms

#### Breadth-First Search (BFS)

BFS explores vertices level by level, starting from a specified vertex, making
it suitable for finding the shortest path and connected components in graphs.

**BFS algorithm steps:**

1. Initialize by placing the starting vertex in a queue and marking it as
   visited.
2. Process each vertex from the queue and explore its unvisited neighbors.
3. Repeat until the queue is empty.

#### Depth-First Search (DFS)

DFS explores as deep as possible along each branch before backtracking, used in
various graph-related problems.

**DFS algorithm steps:**

1. Start at the root and explore along each branch.
2. Backtrack when no further exploration is possible.
3. Continue until all vertices are visited.

#### Greedy Algorithms in Graphs

Greedy algorithms are a type of algorithm that makes the best possible choice at
each step with the aim of finding an overall optimal solution. These algorithms
make decisions based on the current information available, without considering
future consequences. The main concept is to make locally optimal choices at each
step, which may not always result in the most optimal solution, but is often
sufficient for many problems. Dijkstra's algorithm and Prim's algorithm are both
greedy algorithms.

#### Dijkstra's Algorithm

Dijkstra's algorithm is used in weighted graphs to find the shortest path from a
single vertex to all others by iteratively updating path distances.

The idea of Dijkstra's algorithm is to find the minimum spanning tree by
selecting a source vertex, then continuously exploring the nearest unvisted
vertex with the aim of finding the shortest or cheapest path.

#### Prim's Algorithm

Prim’s algorithm is also used in weighted graphs, and builds a minimum spanning
tree (MST) by continuously adding the nearest vertex. The MST is a subset of the
edges that connects all the vertices together without any cycles and with the
minimum possible total edge weight.

A cycle is a non-empty trail for which the first and last vertices are the same.

---

## Big O Notation

Big O Notation is a mathematical notation that describes worst-case runtime
complexity of an algorithm.

### Constant

$$O \left( 1 \right)$$

The ideal runtime as it is constant for any input size. This means that no
matter the size of the input, the runtime is constant.

### Linear

$$O \left( N \right)$$

As the input size grows, the algorithmic runtime increases linearly.

### Logarithmic

$$O \left( \log N \right)$$

Given an arbitrary input size, the runtime is log N of the input size.

### Quadratic

$$O \left( N^2 \right)$$

The runtime grows quadratically with input size. This is typically indicative of
nested loops.

---

## Intro to Data Structures

Data structures are specialized formats for organizing, processing, managing,
and storing data. They are critical for creating efficient software and
algorithms.

**Key data structures:**

- Arrays: Simple lists of elements, accessible by indices.
- Linked Lists: Elements linked with pointers, allowing easy insertion and
  deletion.
- Stacks: Last-In, First-Out (LIFO) data structure.
- Queues: First-In, First-Out (FIFO) data structure.
- Hash Tables: Key-value pairs for efficient data lookup.
- Trees: Hierarchical structures, such as binary search trees.
- Graphs: Sets of nodes connected by edges, useful in modeling networks.

### Arrays

Arrays are the simplest and most widely used data structures. They consist of
elements stored at contiguous memory locations. Each element can be accessed
directly via its index, which makes array operations fast.

Some characteristics include:

- The size of the array is fixed size.
- All elements in the array must be fixed size.

```python
# Creating an array of integers.
integers = [10, 20, 30, 40, 50]

# Accessing the third element.
print(integers[2])  # Output: 30 (Since python indexing starts at 0).
```

### Linked List

Linked Lists are a collection of nodes that together represent a sequence. Each
node contains data and a reference (or link) to the next node in the sequence.
This structure allows for efficient insertion and deletion.

Some characteristics include:

The linked list depends on grow and shrink in size dynamically.

```python
class Node:
    def __init__(self, data):
        self.data = data
        self.next = None


# Creating a simple linked list with 3 elements.
head = Node(1)
head.next = Node(2)
head.next.next = Node(3)
```

### Stacks

A stack is a collection of elements, with two main principal operations: push,
which adds to the collection, and pop, which removes the most recently added
element that was not yet removed. The last element added is the first one to be
removed, hence the LIFO (Last In First Out) behavior.

Some characteristics include:

It follows LIFO (Last In First Out) principle.

```python
stack = []

# Push elements.
stack.append('a')
stack.append('b')
stack.append('c')

# Pop elements.
print(stack.pop())  # Output: c.
print(stack.pop())  # Output: b.
```

### Queues

Queues are similar to stacks but operate in a FIFO (First In First Out) manner.
Elements are added at the back and removed from the front.

Some characteristics include:

It follows FIFO (First In First Out) principle.

```python
from collections import deque

queue = deque()

# Unqueue elements.
queue.append('1')
queue.append('2')
queue.append('c')

# Dequeue elements.
print(queue.pop())  # Output: 1.
```

### Hash Table

Hash tables store data in an associative manner. Data is stored in an array
format, where each data value has its own unique index value. Access of data
becomes very fast if we know the index of the desired data.

```python
# Creating a hash table in Python using dictionary.
my_hash_table = {"name": "John Doe", "age": 29, "email": "john@example.com"}

# Accessing data.
print(my_hash_table["name"])  # Output: John.
```

### Trees

Trees are hierarchical data structures with a root value and subtrees of
children with a parent node, represented as a set of linked nodes.
