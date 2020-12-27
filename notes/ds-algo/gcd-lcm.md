# GCD and LCM

## Table of Contents

- [Find LCM of Two Numbers](#find-lcm-of-two-numbers)
- [Find LCM of Array](#find-lcm-of-given-array-elements)
- [Find GCD of Array](#find-gcd-of-given-array-elements)
- [Given three integers x, y, z, find GCD(LCM(x,y), LCM(x,z))](#find-gcd-of-lcm)

<br/>

## <a name="find-lcm-of-two-numbers"></a>Find LCM of two numbers

```javascript
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

```javascript
function find_lcm(num1, num2) {
  if (num1 > num2) {
    num = num1;
    den = num2;
  } else {
    num = num2;
    den = num1;
  }                   // bigger number needs to be on top

  rem = num % den;    // find remainder of bigger over smaller

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
let result = find_lcm(l[0], l[1]);

for (let i = 2; i < l.length; i++) {
  result = find_lcm(lcm, l[i]);
}

console.log(result);
```

<br/>

## <a name="find-gcd-of-given-array-elements"></a>Find GCD of given array elements

```javascript
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

<br/>

## <a name="find-gcd-of-lcm"></a>Given three integers x, y, z, find GCD(LCM(x,y), LCM(x,z))

**Note:** GCD(LCM(3, 4), LCM(3, 10)) = LCM(3, GCD(4, 10)) = LCM(3, 2) = 6

```Javascript
function find_gcd(a, b) {
  if (a === 0 || b === 0) return 0;
  if (a === b) return a;
  if (a > b) return find_gcd(a-b,b);
  return find_gcd(a, b-a);
}

x = 30, y = 40, z = 400;
g = find_gcd(y, z)
lcm = (x * g)/find_gcd(x, g)
console.log(lcm);
```

<br/>
