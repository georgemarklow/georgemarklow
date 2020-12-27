# String

## Table of Contents

- [Reverse letters in word](#reverse-word)
- [Reverse words in sentence](#reverse-words-in-sentence)
- [Reverse words and letters in sentence](#reverse-words-and-letters-in-sentence)
- [Print all permutations of a string](#print-all-permutations-of-string)
- [Remove adjacent duplicates](#remove-adjacent-duplicates)
- [Check if a string can be obtained by rotating another string 2 places](#string-rotate-2-places)

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

console.log(reverse('george william charles marklow'));   // wolkram selrahc mailliw egroeg

function reverse(s) {
  words = s.split(" ");
  reversed = words.reverse()
    .map(word => {
      return word.split("").reverse().join("");
    })
    .join(" ");
  return reversed;
}

console.log(reverse('george william charles marklow'));  // wolkram selrahc mailliw egroeg
```
<br/>

## <a name="print-all-permutations-of-string"></a>Print all permutations of a string

```Javascript
function permute(a, l, r) {
  if (l === r) {
    console.log(a);
  } else {
    for (let i = l; i < r + 1; i++) {
      a = swap(a,l,i);
      permute(a, l + 1, r);
      a = swap(a,l,i);
    }
  }
}

function swap(a, i, j) {
  charArray = a.split('');
  temp = charArray[i];
  charArray[i] = charArray[j];
  charArray[j] = temp;
  return charArray.join('');
}

text = 'ABC'
n = text.length;
permute(text, 0, n-1);

// ABC
// ACB
// BAC
// BCA
// CBA
// CAB

```

<br/>

## <a name="remove-adjacent-duplicates"></a>Remove adjacent duplicates

e.g. azxxzy -> azzy -> ay

```Javascript
function remove(s, n) {
  chars = s.split('');
  k = 0;
  i = 1;

  while (i < s.length) {
    if (chars[i-1] !== chars[i]) {
      chars[k] = chars[i-1];
      k++;
    } else {
      while (i < chars.length && chars[i-1] === chars[i]) {
        i++;
      }
    }
    i++;
  }

  chars[k] = chars[i-1];
  k++;
  s = chars.join('').substring(k);
  if (k !== n) remove(s, k);
  return s;
}

text = 'DBAABDAB'
remove(text, text.length);   // AB
```

<br/>

## <a name="string-rotate-2-places"></a>Check if a string can be obtained by rotating another string 2 places

#### Anti-Clockwise
Input: string1 = “amazon”, string2 = “azonam”

#### Clockwise
Input: string1 = “amazon”, string2 = “onamaz”

```
function isRotated(str1, str2) {
  if (str1.length !== str2.length) return false;
  clock_rot = ''
  anticlock_rot = ''
  len = str2.length;

  anticlock_rot = anticlock_rot + 
                  str2.substring(len - 2, len) + 
                  str2.substring(0, len - 2);

  clock_rot = clock_rot +
              str2.substring(2) +
              str2.substring(0,2);

  return str1 === clock_rot || str1 === anticlock_rot;
}

console.log(isRotated('amazon','azonam'));   // true
console.log(isRotated('amazon','onamaz'));   // true
```

<br/>
