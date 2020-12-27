# GCD and LCM

## Table of Contents

- [Find LCM of Two Numbers](#find-lcm-of-two-numbers)
- [Find LCM of Given Array Elements](#find-lcm-of-given-array-elements)

<br/>

## <a name="find-lcm-of-two-numbers"></a>Find LCM of two numbers

```
function gcd(a,b) {
  if (a === 0) return b;
  return gcd(b % a, a);
}

function lcm(a,b) {
  return (a / gcd(a,b)) * b;
}

console.log(lcm(15,20))   // 60
```
## <a name="find-lcm-of-given-array-elements"></a>Find LCM of given array elements

```
function find_lcm(num1, num2) {
  if (num1 > num2) {
    num = num1;
    den = num2;
  } else {
    num = num2;
    den = num1;
  }

  rem = num % den;
  while (rem != 0) {
    num = den;
    den = rem;
    rem = num % den;
  }
  gcd = den;
  lcm = Math.trunc(Math.trunc(num1 * num2)/Math.trunc(gcd));
  return lcm;
}

let l = [2, 7, 3, 9, 4];

const num1 = l[0];
const num2 = l[1];
let result = find_lcm(num1, num2);

for (let i = 2; i < l.length; i++) {
  result = find_lcm(lcm, l[i]);
}

console.log(result);
```
