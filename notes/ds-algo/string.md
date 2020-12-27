# String

## Table of Contents

- [Reverse letters in word](#reverse-word)
- [Reverse words in sentence](#reverse-words-in-sentence)
- [Reverse words and letters in sentence](#reverse-words-and-letters-in-sentence)
- [Print all permutations of a string](#print-all-permutations-of-string)
- [Remove adjacent duplicates](#remove-adjacent-duplicates)
- [Check if a string can be obtained by rotating another string 2 places](#string-rotate-2-places)
- [Convert Roman Numerals](#roman-numerals)
- [Check if two strings are anagrams of each other](#strings-anagrams)
- [Remove Duplicates from String](#remove-duplicates)
- [Minimum insertions for palindrome](#min-insertions-palendrome)
- [Length of the longest substring without repeating characters](#longest-substring)

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

```Javascript
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

## <a name="roman-numerals"></a>Convert Roman Numerals

```Javascript
function value(r) {
  switch(r) {
    case 'I': return 1;
    case 'V': return 5;
    case 'X': return 10;
    case 'L': return 50;
    case 'C': return 100;
    case 'D': return 500;
    case 'M': return 1000;
    default: return -1;
  };
}

function convert(str) {
  res = 0;
  for (let i = 0; i < str.length; i++) {
    s1 = value(str[i]);
    if (i + 1 < str.length) {
      s2 = value(str[i + 1])
      if (s1 >= s2) {
        res += s1;
      } else {
        res += s2 - s1;
        i++;
      }
    } else {
      res++;
    }
  }

  return res;
}

console.log(convert('IX'));     // 9
console.log(convert('XL'));     // 40
console.log(convert('MCMIV'));  // 1904
```

<br/>

## <a name="strings-anagrams"></a>Check whether two strings are anagram of each other

**Note:** can sort the strings first and then compare but easier to use the following algorithm

```Javascript
// linear time and constant space
function isAnagram(c, d) {
  if (!c || !d || c.length !== d.length) return false;

  count = 0;
  for (let i = 0; i < c.length; i++) count += c.charCodeAt(i);
  for (let i = 0; i < d.length; i++) count -= d.charCodeAt(i);

  return count === 0;
}

str1 = "cat";
str2 = "tac";
console.log(isAnagram(str1, str2))
```

<br/>

## <a name="remove-duplicates"></a>Remove Duplicates from String

```Javascript
// O(n) time complexity
function removeDuplicates(s) {
  str = '';
  len = s.length;
  for (let i = 0; i < len; i++) {
    c = s[i];
    if (str.indexOf(c) < 0) str += c;
  }
  return str;
}

s = 'aaabbcdd'
console.log(removeDuplicates(s));
```
<br/>


## <a name="min-insertions-palendrome"></a>Minimum insertions for palindrome
```Javascript
// order (n^2)

function findMinInsertions(str, l, h) {

  if (l > h) 
      return Number.MAX_VALUE;
  if (l === h) 
      return 0;
  if (l === h - 1) 
      return (str[l] === str[h]) ? 0 : 1;
  if (str[l] === str[h]) 
      return findMinInsertions(str, l + 1, h - 1);
  else {
    return Math.min(findMinInsertions(str, l, h - 1), findMinInsertions(str, l + 1, h)) + 1;
  }
}

console.log(findMinInsertions('ab', 0, 'ab'.length - 1));       // 1
console.log(findMinInsertions('aa', 0, 'aa'.length - 1));       // 0
console.log(findMinInsertions('abcd', 0, 'abcd'.length - 1));   // 3
console.log(findMinInsertions('abcda', 0, 'abcda'.length - 1)); // 2
console.log(findMinInsertions('abcde', 0, 'abcde'.length - 1)); // 4
```

<br/>

## <a name="longest-substring"></a>Length of the longest substring without repeating characters (Longest distinct characters in the string

O(n + d)
- n is length of the input string
- d is number of characters in input string alphabet

```Javascript
function longestUniqueSubstring(str) {
  n = str.length;
  res = 0

  for (let i = 0; i < str.length; i++) {
    visited = [];

    for (let j = i; j < n; j++) {
      if (visited[str[j]]) break;
      res = Math.max(res, j - i + 1);
      visited[str[j]] = true;
    }

    visited[str[i]] = false;
  }
  return res;
}

console.log(longestUniqueSubstring('ABDEFGABEF'));     // 6
console.log(longestUniqueSubstring('BBBB'));           // 1
console.log(longestUniqueSubstring('GEEKSFORGEEKS'));  // 7
```
