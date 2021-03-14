# Data Structures and Algorithms (JavaScript)

## Table of Contents

- [Time Complexity Order](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#time-complexity)
- [Sorting](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#sorting)
- [Search](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#search)

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

<br/>

### Merge-Sort

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

## Search

- [Linear](https://github.com/georgemarklow/georgemarklow/blob/main/notes/data-structures-and-algorithms.md#linear)
- [Binary]()

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
search(arr, 1); // 2
search(arr, 6); // -1
```

<br>

### Binary
