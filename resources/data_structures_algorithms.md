# Data Structures and Algorithms

---

<details markdown="1">
  <summary>Table of Contents</summary>

-

</details>

---

## Intro to Algorithms

---

Some Popular Algorithms

Binary Search

Binary Search is a searching algorithm used in a sorted array by repeatedly dividing the search interval in half. The idea of binary search is to use the information that the array is sorted and reduce the time complexity to O(log n).

Binary search can be applied when the data structure is sorted and access to any element of the data structure takes constant time.

In Binary Search algorithm:

Divide the search space into two halves by finding the middle index “mid”.
Compare the middle element of the search space with the key.
If the key is found at middle element, the process is terminated.
If the key is not found at middle element, choose which half will be used as the next search space.
If the key is smaller than the middle element, then the left side is used for next search.
If the key is larger than the middle element, then the right side is used for next search.
This process is continued until the key is found or the total search space is exhausted.


Linear Search

Linear Search is defined as a sequential search algorithm that starts at one end and goes through each element of a list until the desired element is found, otherwise the search continues till the end of the data set. The average time complexity is O(n).

In Linear Search algorithm:

Every element is considered as a potential match for the key and checked for the same.
If any element is found equal to the key, the search is successful and the index of that element is returned.
If no element is found equal to the key, the search yields “No match found”.


Sorting Algorithms

Bubble Sort

Bubble Sort is a sorting algorithm that works by repeatedly swapping the adjacent elements if they are in the wrong order. This algorithm is not suitable for large data sets as its average and worst-case time complexity is O(n^2).

In Bubble Sort algorithm:

Traverse from left and compare adjacent elements and the higher one is placed at the right side.
In this way, the largest element is moved to the rightmost end at first.
This process is then continued to find the second largest and place it and so on until the data is  sorted.


Insertion Sort

Insertion sort is a sorting algorithm that works by iteratively inserting each element of an unsorted list into its correct position in a sorted portion of the list. It is a stable sorting algorithm, meaning that elements with equal values maintain their relative order in the sorted output. The time complexity of Insertion Sort is O(n^2).

In Insertion Sort algorithm:

We have to start with the second element of the array as the first element in the array is assumed to be sorted.
Compare the second element with the first element and check if the second element is smaller then swap them.
Move to the third element and compare it with the second element, then the first element and swap as necessary to put it in the correct position among the first three elements.
Continue this process, comparing each element with the ones before it and swapping as needed to place it in the correct position among the sorted elements.
Repeat until the entire array is sorted.


Selection Sort **continue this as incomplete**

Selection sort is a sorting algorithm that works by repeatedly selecting the smallest (or largest) element from the unsorted portion of the list and swapping it with the first element of the unsorted part. This process is repeated for the remaining unsorted portion until the entire list is sorted. As there are two nested loops, the time complexity is O(n^2).

	In Selection Sort algorithm:

The array is divided into two parts,
The algorithm repeatedly selects the minimum (or maximum) element
It swaps the selected element with the first unsorted element
The process continues until the entire array is sorted



Heap Sort
Heap sort is a sorting technique based on Binary Heap data structure. Similar to the selection sort, in heap sort, we first find the minimum element and place the minimum element at the beginning. Repeat the same process for the remaining elements. The time complexity of heap sort is O(n log n).

For Heap Sort algorithm:

First convert the array into heap data structure using heapify, (heapify is the process of creating a heap data structure from a binary tree), then one by one delete the root node of the Max-heap and replace it with the last node in the heap and then heapify the root of the heap. Repeat this process until the size of the heap is greater than 1.

Build a heap from the given input array.
Repeat the following steps until the heap contains only one element:
Swap the root element of the heap (which is the largest element) with the last element of the heap.
Remove the last element of the heap (which is now in the correct position).
Heapify the remaining elements of the heap.
The sorted array is obtained by reversing the order of the elements in the input array.


Divide and Conquer

A divide-and-conquer algorithm recursively breaks down a problem into two or more sub-problems of the same or related type, until these become simple enough to be solved directly.

Quick Sort

QuickSort is a sorting algorithm based on the Divide and Conquer algorithm that picks an element as a pivot and partitions the given array around the picked pivot by placing the pivot in its correct position in the sorted array. The time complexity is O(n^2).

The key process in quickSort is a partition(). The target of partitions is to place the pivot (any element can be chosen to be a pivot) at its correct position in the sorted array and put all smaller elements to the left of the pivot, and all greater elements to the right of the pivot.

Partition is done recursively on each side of the pivot after the pivot is placed in its correct position and this finally sorts the array.





Merge Sort



Graph Algorithms

BFS
DFS
Topological Sort

Greedy
Dijkstra's Algorithm
Prim’s Algorithm
Krukal’s Algorithm


Hashing Algorithms

Recursion

Recursion is the process in which a function calls itself directly and/or indirectly.


Pattern Searching
Searching
Sorting
Bitwise
Recursion
Backtracking
Mathematical
Dynamic Programming

Tree Traversal Techniques:
Inorder
Preorder
Postorder


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
