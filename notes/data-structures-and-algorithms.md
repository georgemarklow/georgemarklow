# Data Structures and Algorithms in Javascript

## Table of Contents

#### Arrays

[Find subarray with given sum](#find-subarray-with-given-sum)

## <a name="find-subarray-with-given-sum"></a> Find subarray with given sum

Find a continuous subarray which adds to a given number.

```
function sort(arr, n, sum) {
  var curr_sum = 0;
  for (let i = 0; i < n; i++) {
    {
      curr_sum = arr[i];
      for (let j = i + 1; j <= n; j++) {
        {
          if (curr_sum === sum) {
            var p = j - 1;
            console.info("Sum found between indexes " + i + " and " + p);
            return;
          }
          if (curr_sum > sum || j === n)
            break;
          curr_sum = curr_sum + arr[j];
        };
      }
    };
  }
  console.info("No subarray found");
  return 0;
}

const arr = [15, 2, 4, 8, 9, 5, 10, 23];
const n = arr.length;
const sum = 23;
sort(arr, n, sum);   // Sum found between indexes 1 and 4 
```
