# GCD and LCM

## Table of Contents

- [Find LCM of Two Numbers](#find-lcm-of-two-numbers)
- [Find LCM of Array](#find-lcm-of-given-array-elements)
- [Find GCD of Array](#find-gcd-of-given-array-elements)

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
<br/>

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

  while (rem !== 0) {
    num = den;
    den = rem;
    rem = num % den;
  }
  gcd = den;
  lcm = Math.trunc(Math.trunc(num1 * num2) / Math.trunc(gcd));
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

<br/>

## <a name="find-gcd-of-given-array-elements"></a>Find GCD of given array elements

```
function find_gcd(x, y) {
  while(y) {
    temp = x;
    x = y;
    y = temp % y;
  }
  return x;
}

l = [2,4,6,8,16];
gcd = find_gcd(l[0], l[1]);

for (let i = 2; i < i.length; i++) {
  gcd = find_gcd(gcd, l[i]);
}

console.log(gcd);
```
