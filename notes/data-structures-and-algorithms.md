# Data Structures and Algorithms in Javascript

## Table of Contents

#### Arrays

- [Find subarray with given sum](#find-subarray-with-given-sum)
- [Count the triplets](#count-the-triplets)
- [Kadane’s Algorithm (Largest Sum Contiguous Subarray)](#kadanes-algorithm)

<br/>

## <a name="find-subarray-with-given-sum"></a>Find subarray with given sum

Find a continuous subarray which adds to a given number.

1. Go through each element i in the array, starting a current sum variable
2. From each element, iterate forward j until (a) sum === required or (b) sum > required i.e. break out to next i
3. Keep a record of current sum in i loop

```javascript
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

<br/>

## <a name="count-the-triplets"></a>Count the triplets

[Todo]

<br/>

## <a name="kadanes-algorithm"></a>Kadane’s Algorithm (Largest Sum Contiguous Subarray)

Find the sum of contiguous subarray within a one-dimensional array of numbers which has the largest sum.

1. Look for all positive contiguous segments of the array
2. Keep track of maximum sum contiguous segment among all positive segments
3. Each time we get a positive sum compare it with max_so_far and update max_so_far if it is greater than max_so_far

```javascript
function maxSubArraySum(a) {
  size = a.length;
  max_so_far = 0;
  max_ending_here = 0;

  for (i = 0; i < size; i++) {
    max_ending_here = max_ending_here + a[i];
    if (max_ending_here < 0) max_ending_here = 0;
    else if (max_so_far < max_ending_here) max_so_far = max_ending_here
  }
  return max_so_far
}

a = [-2, -3, 4, -1, -2, 1, 5, -3];
maxSubArraySum(a)   // 7
```
<br/>

| Complexity      | Description |
| ----------- | ----------- |
| Time   | O(n)        |

<br/>

This code handles the case where all values in the array are negative as well:

```javascript
function maxSubArraySum(a) {
  curr_max = a[0];
  max_so_far = a[0];

  for (i = 1; i < a.length; i++) {
    curr_max = Math.max(a[i], curr_max + a[i])
    max_so_far = Math.max(max_so_far, curr_max)
  }
  return max_so_far
}

a = [-2, -3, 4, -1, -2, 1, 5, -3];
maxSubArraySum(a)   // 7
```
