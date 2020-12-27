# GCD and LCM

### Table of Contents

- [Find LCM of Two Numbers]()

## Find LCM of Two Numbers

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
