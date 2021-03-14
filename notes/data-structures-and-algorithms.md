# Data Structures and Algorithms (JavaScript)

## Table of Contents

- [Time Complexity Order](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#time-complexity)
- [Sorting](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#sorting)
- [Search](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#search)
- [Stack](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#stack)
- [Queue](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#queue)
- [Dictionary / Map](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#dictionary)
- [Set](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#set)
- [Counter](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#counter)

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
- [Selection-Sort](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#selection-sort)
- [Insertion-Sort](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#insertion-sort)
- [Merge-Sort](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#merge-sort)
- [Quick-Sort](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#quick-sort)

<br>

### Summary

| Algorithm   |      Ideal for |
|:----------|:-------------|
|- Bubble-Sort<br>- Insertion-Sort<br>- Selection-Sort  | small datasets but slow with large datasets |
|- Merge-Sort<br>- Quick-Sort<br>- Heap-Sort | large data but overkill for small data |

<br/>

### Bubble-Sort

- Slowest for sorting
- Easy to implement 
- Ideal for small data
- Compares each pair of adjacent values
- After the first pass, the largest value is in the right-most position

![Screenshot 2021-03-14 at 4 34 50 pm](https://user-images.githubusercontent.com/11710404/111076196-3bc2d900-84e3-11eb-9588-f1449441d14b.png)

<br>

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
![Screenshot 2021-03-14 at 4 33 40 pm](https://user-images.githubusercontent.com/11710404/111076156-0cac6780-84e3-11eb-9f96-6e80ca486363.png)

<br/>

### Selection-Sort

- Traverse the unsorted array
- Put the largest value at the end of it
- Repeated (n-1) times
- Quadratic time complexity but performs better than bubble and selection sorts as a smaller number of swaps are required

![Screenshot 2021-03-14 at 4 37 40 pm](https://user-images.githubusercontent.com/11710404/111076278-9c521600-84e3-11eb-9040-a7c2da1fe144.png)

<br>

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

![Screenshot 2021-03-14 at 4 37 17 pm](https://user-images.githubusercontent.com/11710404/111076270-92301780-84e3-11eb-8657-ae34f4ec03b7.png)

<br/>

### Insertion-Sort

- Same O(n<sup>2</sup>) time complexity as Bubble-Sort but performs better
- Like arranging playing cards, we keep a sorted sub-array
- Each value inserted into its proper position in the sorted sub-array

![Screenshot 2021-03-14 at 4 40 14 pm](https://user-images.githubusercontent.com/11710404/111076374-f9e66280-84e3-11eb-91c3-93312e2f790f.png)

<br>

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

![Screenshot 2021-03-14 at 4 39 50 pm](https://user-images.githubusercontent.com/11710404/111076361-eb984680-84e3-11eb-99ee-adfebcd8019a.png)

<br/>

### Merge-Sort

- Divide and Conquer algorithm
- Divide the input into two halves recursively
- In each step, data is divided into two halves
- The two parts are sorted separately
- Finally, combine the result into the final sorted output


```javascript
function util(arr, temp, l, mid, u, compare) {
    let l1 = l;
    const l2 = mid;
    let u1 = mid + 1;
    const u2 = u;
    let count = l;

    while (l1 <= l2 && u1 <= u2) {
        if (compare(arr[l1], arr[u1])) {
            temp[count++] = arr[l1++];
        } else {
            temp[count++] = arr[u1++];
        }
    };

    while (l1 <= l2) temp[count++] = arr[l1++];
    while (u1 <= u2) temp[count++] = arr[u1++];
    for (let i = l; i <= u; i++) arr[i] = temp[i];
}

function mergeSort(arr, temp, l, u, compare) {
    if (l >= u) return;
    const mid = Math.floor((l + u) / 2);
    mergeSort(arr, temp, l, mid, compare);
    mergeSort(arr, temp, mid + 1, u, compare);
    util(arr, temp, l, mid, u, compare);
};

function sort(arr, compare) {
    const size = arr.length;
    const temp = new Array(size);
    mergeSort(arr, temp, 0, size - 1, compare);
}

const arr = [5,3,1,2,4];
const more = (array1, array2) => array1 > array2;
sort(arr, more);
console.log(arr.join(" "));
```

![Screenshot 2021-03-14 at 4 41 48 pm](https://user-images.githubusercontent.com/11710404/111076440-31550f00-84e4-11eb-9f52-e401f8e464eb.png)

<br/>

### Quick-Sort

```javascript
const swap = (arr, first, second) => {
    const temp = arr[first];
    arr[first] = arr[second];
    arr[second] = temp;
}

function quickSortUtil(arr, l, u) {
    if (u <= l) return;
    const pivot = arr[l];
    const p1 = l;
    const p2 = u;

    while (l < u) {
        while (arr[l] <= pivot && l < u) l++;
        while (arr[u] > pivot && l <= u) u--;
        if (l < u) swap(arr, u, l);
    }

    swap(arr, u, p1);
    quickSortUtil(arr, p1, u - 1);
    quickSortUtil(arr, u + 1, p2);
}

function quickSort(arr) {
    const size = arr.length;
    quickSortUtil(arr, 0, size - 1);
}

const arr = [5,3,1,4,2];
quickSort(arr);
console.log(arr.join(' '));
```

<br>

## Search

- [Linear](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#linear)
- [Binary](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#binary)

<br>

### Linear

```javascript
function search(arr, x) {
    for (let i = 0; i < arr.length; i++) {
        if (arr[i] === x) return i; 
    }
    return -1;
}

const arr = [5,3,1,4,2]
search(arr, 1);         // 2
search(arr, 6);         // -1
```

<br>

### Binary

```javascript
function search(arr, l, r, x) {
    while (l <= r) {
        const mid = Math.floor(l + (r - 1));
        if (arr[mid] === x) return mid
        else if (arr[mid] < x) l = mid + 1
        else r = mid - 1
    }
    return -1;
}

const arr = [5,3,1,4,2]
search(arr, 0, arr.length, 1);    
search(arr, 6);                 // 2
search(arr, 6);                 // -1
```
<br>

## Stack

All stack operations are O(1).

Applications:
- Recursion
- Postfix evaluation
- Backtracking
- Depth-first search
- Convert decimal to a number
<br>

```javascript
class Stack {
   constructor() {
       this.items = [];
   }
 
   push(item) {
       this.items.push(item);
       return this.items;
   }
 
   pop() {
       return this.items.pop();
   }
 
   peek() {
       return this.items[this.items.length - 1];
   }
 
   isEmpty() {
       return this.items.length === 0;
   }
}
 
const stack = new Stack();
stack.push(1);             // [1]
stack.push(2);             // [1, 2]
stack.pop();               // 2
stack.peek();              // 1
stack.pop()                // 1
stack.isEmpty()            // true
```

<br>

## Queue

All queue operations are O(1).

- Access shared resource (printer)
- Multiprogramming
- Message queue
- A breadth-first traversal of a graph

<br>

```javascript
class Queue {
   constructor() {
       this.items = [];
   }
 
   push(item) {
       this.items.unshift(item);
       return this.items;
   }
 
   peek() {
       return this.items[this.items.length - 1];
   }
 
   pop() {
       return this.items.pop();
   }
 
   isEmpty() {
       return this.items === 0;
   }
}
 
const queue = new Queue();
queue.push(1);             // [1]
queue.push(2);             // [2, 1]
queue.pop();               // 1
queue.peek();              // 2
queue.pop();               // 2
queue.isEmpty();           // true

```

<br>

## Dictionary

- Maps keys to values
- Uses a hash-table => key-value pairs not in sorted order
- Does not allow duplicate keys 
- Values can be duplicates

<br>

```javascript
class Dictionary {
   constructor() {
       this.items = {}
   }
 
   add(key, value) {
       if (this.items[key]) {
           throw new Error('Key already added')
       }
       this.items[key] = value
       return this.items
   }
 
   remove(key) {
       if (!this.items.hasOwnProperty(key)) {
           throw new Error('Invalid map key')
       }
       const value = this.items[key];
       delete this.items[key]
       return {key, value}
   }
 
   keys() {
       return Object.keys(this.items)
   }
 
   values() {
       return Object.values(this.items)
   }
 
   exists(value) {
       return this.items.hasOwnProperty(value)
   }
}
 
const d = new Dictionary();
d.add('a',10);            // { a: 10 }
d.add('b',20);            // { a: 10, b: 20 }
d.keys();                 // ['a','b']
d.values();               // [ 10, 20 ]
d.remove('a')             // 10
d.exists('b')             // true
d.exists('a')             // false
d.add('a',30)             // Key already added
d.remove('c')             // Invalid map key

```

<br>

## Set
- Stores only unique elements
- Implemented using a hash-table
- Elements not stored in sequential order
- Like dictionaries (maps) but stores only keys

Applications:
- Removing duplicate data from collections

```javascript
const s = new Set(); // in JavaScript already
s.add('a')
s.add('a')
s.add('b')
s                   // Set { 'a', 'b' }
s.size              // 2
s.has('a')          // true
s.has('c')          // false
s.delete('a')
 
for (let [key, value] of s.entries()) {
    console.log(key)  // b
}
 
for (let item of s) console.log(item) // b
 
s.clear()          
s                   // Set {}

```

<br>

## Counter
Counts the number of occurrences of a value in a list.

```javascript
class CountMap {
 constructor() {
   this.items = new Map()
 }
 
 insert(key) {
   if (this.items.has(key)) {
     const count = this.items.get(key)
     this.items.set(key, count + 1)
   } else {
     this.items.set(key, 1)
   }
 }
 
 remove(key) {
   if (this.items.has(key)) {
     if (this.items.get(key) === 1) {
       this.items.delete(key)
     } else {
       const count = this.items.get(key)
       this.items.set(key, count - 1)
     }
   }
 }
  get(key) {
     if (this.items.has(key))
       return this.items.get(key)
     return 0
   }
 
   exists(key) {
     return this.items.has(key)
   }
}
 
const c = new CountMap();
c.insert('a')
c.insert('a')
c.insert('b')
c                 // CountMap { items: Map { 'a' => 2, 'b' => 1 } }
c.get('a')        // 2
c.exists('a')     // true
c.exists('c')     // false

```
