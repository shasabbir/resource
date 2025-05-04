
# 🐍 Python Data Structures Cheatsheet

## Navigation
- [1. Arrays](#1-arrays)
- [2. Linked Lists](#2-linked-lists)
- [3. HashMaps](#3-hashmaps)
- [4. Stacks](#4-stacks)
- [5. Queues](#5-queues)
- [6. Trees](#6-trees)
- [7. Graphs](#7-graphs)

---

## 1. Arrays

### Basic Usage
Arrays (or lists in Python) are ordered collections of items.

```python
arr = [1, 2, 3]  # Initializing a list with 3 elements
arr.append(4)  # Adds 4 to the end of the list
arr.pop()  # Removes and returns the last element (4)
arr.insert(1, 99)  # Inserts 99 at index 1, shifting other elements
del arr[0]  # Deletes the element at index 0
```

### Common Functions
Python lists have many built-in functions for easy manipulation:

```python
len(arr)  # Returns the length of the list
sum(arr)  # Returns the sum of all elements in the list
sorted(arr)  # Returns a sorted copy of the list
min(arr)  # Returns the minimum element in the list
max(arr)  # Returns the maximum element in the list
```

### List Comprehension
A concise way to create lists by applying an expression to each element in a sequence.

```python
squares = [x**2 for x in range(10)]  # Creates a list of squares from 0 to 9
```

---

## 2. Linked Lists

### Node Definition
A linked list consists of nodes where each node contains a value and a reference (link) to the next node.

```python
class Node:
    def __init__(self, val):
        self.val = val  # Stores the value
        self.next = None  # Stores the reference to the next node
```

### Linked List Operations
This method traverses and prints each node in the list.

```python
def print_list(head):
    while head:  # Loop until we reach the end (None)
        print(head.val)  # Print the current node's value
        head = head.next  # Move to the next node
```

### Reversal
Reverses a singly linked list by adjusting the `next` pointers.

```python
def reverse(head):
    prev = None  # Keeps track of the previous node
    while head:  # Traverse the list
        nxt = head.next  # Stores the reference to the next node
        head.next = prev  # Reverses the direction of the link
        prev = head  # Move prev to the current node
        head = nxt  # Move to the next node
    return prev  # prev will be the new head of the reversed list
```

---

## 3. HashMaps

### Basic Dictionary Usage
Python’s `dict` (hash map) allows key-value pairs.

```python
d = {'a': 1, 'b': 2}  # Creating a dictionary with keys 'a' and 'b'
d['c'] = 3  # Adds a new key-value pair ('c', 3)
print(d.get('a', 0))  # Retrieves value for 'a', default is 0 if not found
del d['b']  # Removes the key 'b' and its associated value
```

### Useful Methods
Dictionaries offer several built-in methods to manage data.

```python
d.keys()  # Returns a list of all keys
d.values()  # Returns a list of all values
d.items()  # Returns a list of all key-value pairs as tuples
d.clear()  # Removes all elements from the dictionary
```

### DefaultDict
A variant of the dictionary that provides a default value for missing keys.

```python
from collections import defaultdict
dd = defaultdict(int)  # Default value is 0 for missing keys
dd['key'] += 1  # Increments the value of 'key', which starts at 0
```

---

## 4. Stacks

### Using List
Stacks follow the Last In, First Out (LIFO) principle. We can implement a stack using a list.

```python
stack = []  # Initialize an empty stack
stack.append(1)  # Push 1 onto the stack
stack.append(2)  # Push 2 onto the stack
stack.pop()  # Pops 2 from the stack
```

### Using deque
`deque` from the `collections` module provides an efficient stack implementation.

```python
from collections import deque
stack = deque()  # Initialize a deque as a stack
stack.append(1)  # Push 1 onto the stack
stack.pop()  # Pops 1 from the stack
```

---

## 5. Queues

### Using deque
Queues follow the First In, First Out (FIFO) principle. We can implement a queue using a `deque`.

```python
from collections import deque
queue = deque()  # Initialize an empty queue
queue.append(1)  # Enqueue 1
queue.popleft()  # Dequeues 1 from the queue
```

### Priority Queue
A priority queue allows elements with higher priority to be dequeued first.

```python
import heapq
heap = []  # Initialize an empty heap
heapq.heappush(heap, 1)  # Adds 1 to the priority queue
heapq.heappop(heap)  # Pops the smallest element (1) from the heap
```

---

## 6. Trees

### Node Definition
In a tree, each node has a value and references to its left and right children.

```python
class TreeNode:
    def __init__(self, val=0, left=None, right=None):
        self.val = val  # Stores the value of the node
        self.left = left  # Reference to the left child
        self.right = right  # Reference to the right child
```

### Traversals
This method performs an **in-order** traversal (left → root → right).

```python
def inorder(node):
    if node:  # Check if the node is not None
        inorder(node.left)  # Traverse the left subtree
        print(node.val)  # Print the value of the current node
        inorder(node.right)  # Traverse the right subtree
```

### Level Order
Level-order traversal visits nodes level by level (BFS).

```python
from collections import deque
def level_order(root):
    q = deque([root])  # Initialize a queue with the root node
    while q:
        node = q.popleft()  # Dequeue a node
        print(node.val)  # Print the node's value
        if node.left:  # Enqueue the left child if it exists
            q.append(node.left)
        if node.right:  # Enqueue the right child if it exists
            q.append(node.right)
```

---

## 7. Graphs

### Representation
Graphs are represented using **adjacency lists** in Python.

```python
graph = {'A': ['B', 'C'], 'B': ['D'], 'C': ['D'], 'D': []}  # Directed graph
```

### DFS
Depth-First Search (DFS) explores as far as possible down one branch before backtracking.

```python
def dfs(graph, node, visited=set()):
    if node in visited:  # Return if the node has been visited
        return
    visited.add(node)  # Mark the current node as visited
    for neighbor in graph[node]:  # Visit each neighboring node
        dfs(graph, neighbor, visited)
```

### BFS
Breadth-First Search (BFS) explores all nodes at the present depth level before moving on to nodes at the next depth level.

```python
from collections import deque
def bfs(graph, start):
    q = deque([start])  # Initialize a queue with the start node
    visited = set()  # Initialize an empty set to track visited nodes
    while q:
        node = q.popleft()  # Dequeue a node
        if node not in visited:  # If the node has not been visited
            visited.add(node)  # Mark the node as visited
            for neighbor in graph[node]:  # Enqueue all neighbors
                q.append(neighbor)
```

---
