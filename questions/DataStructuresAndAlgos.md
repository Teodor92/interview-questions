# Data Structures and Algorithms

## 1. Can you name a few data structures? What are they used form?

List, LinkedList, Map, Set, Bag, Tree, Graph

## 2. What is the difference between Set, Map and List?

### Set
- **Uniqueness:** A Set is a collection that cannot contain duplicate elements. 
- **Usage:** It's typically used for membership testing, removing duplicates from a collection, and performing mathematical operations like union, intersection.
- **Ordering:** Most Set implementations do not maintain the order of elements.

### Map
- **Key-Value Pairs:** A Map is a collection that stores elements in key-value pairs. Each key maps to a specific value.
- **Lookup Efficiency:** It's designed for efficient retrieval of values based on their keys.
- **Uniqueness:** Keys are unique in the Map, but values can be duplicated.

### List
- **Ordered Collection:** A List is an ordered sequence of elements. The elements can be accessed by their integer index.
- **Duplicates:** It allows duplicate elements and maintains the insertion order.
- **Functionality:** It's typically used for storing and accessing elements in a sequence, with functionalities like add, remove, and get based on index.

Overall, while Sets ensure uniqueness and Maps associate keys with values, Lists maintain a sequence of elements, potentially including duplicates.

## 3. When should we use a DFS and BFS?

### DFS (Depth-First Search)

- **Use Case:**
  - DFS is used when we want to explore as far as possible along a branch before backtracking.
  - It's useful in scenarios like solving puzzles, where you want to explore all possible paths to find a solution.
- **Advantages:**
  - DFS requires less memory as it is not necessary to store all the child pointers at each level.
  - It's easier to implement recursively.
- **Scenarios:**
  - Finding connected components in a graph.
  - Topological sorting in a directed graph.
  - Solving puzzles and mazes.

### BFS (Breadth-First Search)

- **Use Case:**
  - BFS is used when we want to explore all neighbors at one depth before moving to the next level.
  - It's effective in finding the shortest path in terms of the number of edges.
- **Advantages:**
  - BFS can find the shortest path in unweighted graphs and is often used in scenarios like GPS navigation.
  - It's useful in peer-to-peer networks, crawlers in search engines, and broadcasting in networks.
- **Scenarios:**
  - Finding the shortest path in unweighted graphs.
  - Level order traversal in trees.
  - Detecting cycles in a graph.

In summary, choose DFS for exploring all paths or when memory is a concern, and BFS for shortest path problems or when exploring nodes level by level.
