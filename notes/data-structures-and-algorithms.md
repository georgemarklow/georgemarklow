# Data Structures and Algorithms (JavaScript)

## Table of Contents

- [Time Complexity Order](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#time-complexity)

<br/>

## Time Complexity

### Time Complexity

| Name   |      Notation      | Examples |
|:----------|:-------------|:-------------|
| Constant | O(1)  | - Access nth element in array<br>- Push/pop of a stack<br>- Add/remove queue element<br>- Access hashtable element   |
| Logarithmic |  O(log n)     | - Array operations (search/min/max)<br>- Linked list (traversal/min/max)  |
| Linear | O(n) | - Binary search |
| N-LogN | (n log n) | - Merge-sort<br>- Quick-sort (average)<br>- Heap-Sort  |
| Quadratic | O(n<sup>2</sup>) |- Bubble-osrt<br>- Selection-sort<br>- Insertion-sort|
| Polynomial | O(n<sup>c</sup>) c constant > 1 ||
| Exponential | O(c<sup>m</sup>) c constant > 1 | All possible subsets |
| Factorial | O(n!) / O(n<sup>n</sup>) | All possible permutations |

<br/>

### Running Time Analysis

| Name   |      Running Time  |
|:----------|:-------------|
| Loop  | O(n) |
| Nested Loop | O(n<sup>2</sup> |
| Consecutive statements | Sum of running times |
| If-Else | Consider running time of larger block |
| Logarithmic | Input size descreased by constant factor on each iteration |
