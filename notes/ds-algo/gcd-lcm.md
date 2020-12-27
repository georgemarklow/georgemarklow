# GCD and LCM

## Table of Contents

- [Find LCM of Two Numbers](#find-lcm-of-two-numbers)

<br/>

#### Find LCM of Two Numbers
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
