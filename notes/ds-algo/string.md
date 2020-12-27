# String

## Table of Contents

- [Reverse letters in word](#reverse-word)
- [Reverse words in sentence](#reverse-words-in-sentence)
- [Reverse words and letters in sentence](#reverse-words-and-letters-in-sentence)

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

<br/>

## <a name="reverse-words-in-sentence"></a>Reverse words in sentence

```Javascript
function reverseWordsInString1(s){
  words = s.split(" ");
  words.reverse();
  return words.join(" ");
}

console.log(reverseWordsInString1('george william charles marklow'))   // marklow charles william george

function reverseWordsInString2(s) {
  words = s.split(" ");
  start = 0;
  end = words.length - 1;

  while(start < end) {
    temp = words[start];
    words[start] = words[end];
    words[end] = temp;
    start++;
    end--;
  }

  return words.join(" ");
}

console.log(reverseWordsInString2('george william charles marklow'))   // marklow charles william george

```
<br/>

## <a name="reverse-words-and-letters-in-sentence"></a>Reverse words and letters in sentence

```Javascript
function reverse(s) {
  result = '';
  for (let i = s.length - 1; i >= 0; i--) {
    result += s[i];
  }
  return result;
}

console.log(reverse('george william charles marklow'));
```
