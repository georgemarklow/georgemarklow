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

<br/>

## Sorting

- [Bubble-Sort](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#bubble-sort)
- [Selection-Sort]()
- [Insertion-Sort]()
- [Bubble-Sort]()
- [Quick-Sort]()
- [Merge-Sort]()

<br/>

### Bubble-Sort

```javascript
function sort(arr, compare) {
    let size = arr.length;
    let swapped = true;
    let temp;
    for (let i = 0; i < (size - 1) && swapped; i++) {
        for (let j = 0; j < size - i - 1; j++) {
            if (compare(arr[j], arr[j + 1])) {
                temp = arr[j];
                arr[j] = arr[j + 1];
                arr[j + 1] = temp;
                swapped = true;
            }
        }
    }
}

const more = (value1, value2) => value1 > value2;
const arr = [5,3,1,2,4];
sort(arr, more);
console.log(arr.join(' '));
```

<br/>

### Selection-Sort

```javascript
function sort(arr, compare) {
    const size = arr.length;
    let max;
    let temp;
    for (let i = 0; i < size - 1; i++) {
        max = 0;
        for (let j = 1; j < size - i; j++) {
            if (compare(arr[j], arr[max])) {
                max = j;
            }
        }
        temp = arr[size - 1 - i];
        arr[size - 1 - i] = arr[max];
        arr[max] = temp;
    }
}

const more = (array1, array2) => array1 > array2;
const arr = [5, 3, 1, 2, 4]
sort(arr, more);
console.log(arr.join(' '));
```

<br/>

### Insertion-Sort

```javascript
function sort(arr, compare) {
    const size = arr.length;
    let temp;
    for (let i = 0; i < size; i++) {
        temp = arr[i];
        let j;
        for (j = i; j > 0 && compare(arr[j - 1], temp); j--) {
            arr[j] = arr[j - 1];
        }
        arr[j] = temp;
    }
}

const more = (value1, value2) => value1 < value2;
const arr = [5, 3, 1,2 ,4]
sort(arr, more);
console.log(arr.join(' '));
```
