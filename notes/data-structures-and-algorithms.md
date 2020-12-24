# Data Structures and Algorithms in Javascript

## Table of Contents

#### Arrays

[Find subarray with given sum](#find-subarray-with-given-sum)

## <a name="find-subarray-with-given-sum"></a> Find subarray with given sum

Find a continuous subarray which adds to a given number.

1. Go through each element i in the array, starting a current sum variable
2. From each element, iterate forward j until (a) sum === required or (b) sum > required i.e. break out to next i
3. Keep a record of current sum in i loop

```
function find(arr, n, sum) {
  for (i = 0; i < n; i++) {
    curr_sum = arr[i];
    for (j = i + 1; j < n; j++) {
      curr_sum = curr_sum + arr[j]
      if (curr_sum === sum) {
        console.log(`between indices ${i} and ${j}`)
        return
      }
      if (curr_sum > sum) break;
    }
  }
  console.log('not found')
}

arr1 = [1, 4, 20, 3, 10, 5] 
arr2 = [1, 4, 0, 0, 3, 10, 5]
arr3 = [1, 4]

find(arr1, arr1.length, 33)  // between indices 2 and 4
find(arr2, arr2.length, 7)   // between indices 1 and 4
find(arr3, arr3.length, 0)   // not found
```

<br/>

| Complexity      | Description |
| ----------- | ----------- |
| Space      | O(n<sup>2</sup>) in worst case |
| Time   | O(1) as constant extra space needed        |
