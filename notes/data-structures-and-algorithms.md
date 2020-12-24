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
def find(arr, n, sum): 
    for i in range(n): 
        curr_sum = arr[i] 
        j = i + 1
        while j <= n: 
            if curr_sum == sum: 
                print ("Sum found between") 
                print("indexes % d and % d"%(i, j-1)) 
                return
            if curr_sum > sum or j == n: 
                break
            curr_sum = curr_sum + arr[j] 
            j += 1
    print ("No subarray found") 
    return
  
arr = [15, 2, 4, 8, 9, 5, 10, 23] 
n = len(arr) 
sum = 23
find(arr, n, sum)
```

<br/>

| Complexity      | Description |
| ----------- | ----------- |
| Space      | O(n^2) in worst case |
| Time   | O(1) as constant extra space needed        |
