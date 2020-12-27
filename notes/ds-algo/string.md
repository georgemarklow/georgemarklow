# String

## Table of Contents

- [Reverse letters in word](#reverse-word)

<br/>

## <a name="reverse-word"></a>Reverse letters in word

```Javascript
function reverse1(s) {
  return s.split("").reverse().join("");
}

console.log(reverse1('george'));   // egroeg

function reverse2(s) {
  result = '';
  for (let i = s.length - 1; i >= 0; i--) {
    result += s[i];
  }
  return result;   // egroeg
}

console.log(reverse2('george'));

```
