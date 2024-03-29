<p align="center">
  <img src="https://user-images.githubusercontent.com/11710404/111040646-da8bfe80-842b-11eb-9d5c-62959f5b66d3.png" />
</p>

# Books
- [JavaScript for impatient programmers](https://exploringjs.com/impatient-js/toc.html)

# Javascript

<br/>

## Warm-Up Drill with Node.js

Drills cover important operations of a programming language or framework in a very short space of time.

What drills are for:
-  They get you upto speed quickly on a language if you've been away from it for a while e.g. for returning to front-end development after a few months working on a middleware webservices project in Java/C#.
-  Preparing you for something done under timed conditions, such as a hackathon.
-  They expose differences between operations through examples e.g. toPrecision() vs. toFixed()

What drills are **not** for:
- Because they are to be worked through quickly, and aren't broken up with descriptions of everything going on, they aren't ideal for people new to programming.

<br/>

There's two ways to get started with this JavaScript drill, using:
1. Node.js from the Terminal
2. A Node.js Replit playground (a collaborative space for experimenting with and sharing code)

For one-liners, such as string and number manipulation, I prefer using the Terminal. For longer examples that use multiple lines, I find it more convenient to use Replit.

<br/>

### Option 1: Node.js from the Terminal

1. Install Node from [here](https://nodejs.org/en/download/)
2. Press ⌘ + Space, search and open the Terminal
3. Type "node" and press Enter
4. Write some basic arithmetic and press Enter again to display the result

<img width="777" alt="Screenshot 2021-03-13 at 6 24 31 pm" src="https://user-images.githubusercontent.com/11710404/111040077-5f294d80-8429-11eb-985f-1a583baf9192.png">


### Option 2: A Node.js Replit Playground

1. Visit [Replit](https://replit.com/~)

<img width="1381" alt="Screenshot 2021-03-13 at 6 18 08 pm" src="https://user-images.githubusercontent.com/11710404/111039988-ed510400-8428-11eb-81a3-97b7529063dc.png">

2. Create a new Node.js Repl

<img width="1381" alt="Screenshot 2021-03-13 at 6 19 26 pm" src="https://user-images.githubusercontent.com/11710404/111039986-e5915f80-8428-11eb-9d2f-08f393ad24c5.png">

3. Type some code and hit the green Run button at the top

<img width="1193" alt="Screenshot 2021-03-13 at 6 20 27 pm" src="https://user-images.githubusercontent.com/11710404/111039978-dca08e00-8428-11eb-8993-50df22bb964a.png">

Let's get started, shall we?

<br/>

### Contents
- [Console Basics](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#console-basics)
- [Strings](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#strings)
- [Numbers](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#numbers)
- [Functions](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#functions)
- [Arrays](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#arrays)
- [Math Library](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#math-library)
- [JSON](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#json)

<br/>

### Console Basics

```javascript
console.log('test', 123, true);               // test 123 true
console.log('Test: %s %j', 123, 'test');      // Test: 123 "test"
console.log('%s %s', 'test', 123);            // test 123
console.log('%o', {foo: 123, bar: 'test'});   // { foo: 123, bar: 'test' }
console.log('%j', {foo: 123, bar: 'test'});   // {"foo":123,"bar":"test"}
console.log('%s%%', 99);                      // 99%
console.log(JSON.stringify(
  {first: 'George', last: 'Marklow'}
, null, 2));                                  // { "first": "George", "last": "Marklow" }
```

<br/>

### Strings

```javascript
const s = 'Abc'     
const t = ' def '   
                   
```
```javascript
s                   // 'Abc'
s.toLowerCase()     // 'abc'
s.toUpperCase()     // 'ABC'
s.length            // 3
s[0]                // 'A'
s[s.length - 1]     // 'c'
s[3]                // undefined
s[-1]               // undefined
```
```javascript
s.charAt(1)         // 'b'
s.charAt(3)         // ''
```
```javascript
s.substring(0,2)    // 'Ab'
s.substring(0,3)    // 'Abc'
s.substring(0,4)    // 'Abc'
s.substring(2)      // 'c'
s.substring(3)      // ''
```
```javascript
s+t                 // 'Abc def '
`s: ${s}`           // 's: Abc'
t.trimStart()       // 'def '
t.trimEnd()         // ' def'
t.trim()            // 'def'
```
```javascript
t.replace('f','F')  // ' deF '
t.replace('z','Z')  // ' def '
```
```javascript
s.startsWith('A')   // true
s.startsWith('a')   // false
s.endsWith('c')     // true
s.endsWith('x')     // false
```
```javascript
s.concat('abc')     // 'Abcabc'
s.indexOf('c')      // 2
s.indexOf('C')      // -1
s.lastIndexOf('c')  // 2
s.lastIndexOf('C')  // -1
```
```javascript
const u = 'Abc'     // undefined
s.localeCompare(u)  // 0
u.localeCompare(s)  // 0
s.localeCompare(u, 'en', { sensitivity: 'base' })   // 0
```
```javascript
String.fromCharCode(65,98,99)                       // 'Abc'
String.fromCharCode(32,100,101,102,32)              // ' def '
```

<br/>

### Numbers

```javascript
const a = 2;
const b = "3";
const c = Math.PI;
const d = 123.456;
```
```javascript
a + 3;                       // 5
a - 3;                       // -1
a * 2;                       // 4
a * 1.25;                    // 2.5
a / 2;                       // 1
a / 3;                       // 0.6666666666666666
a % 2;                       // 0
a % 3;                       // 2
a ** 2;                      // 4
a ** 1.5;                    // 2.82842712474619
```
```javascript
`d: ${d}`;                   // 'd: 123.456'
d.toString();                // '123.456'
d.toString(16);              // '7b.74bc6a7ef9dc'
d.toString(2);               // '1111011.0111010010111100011010100111111011111001110111'
```
```javascript
Number.parseInt(b);          // 3
Number.parseFloat(b);        // 3
Number.parseInt(a);          // 2
Number.parseInt(d);          // 123
Number.parseInt(a, 10);      // 2
Number.parseFloat(a);        // 2
Number.parseFloat(d);        // 123.456
```
```javascript
a + b;                       // '23'
b + a;                       // '32'
a + parseInt(b);             // 5
```
```javascript
c.toFixed();                 // '3'
c.toFixed(0);                // '3'
c.toFixed(1);                // '3.1'
c.toFixed(2);                // '3.14'
c.toFixed(3);                // '3.142'
d.toFixed();                 // '123'
d.toFixed(0);                // '123'
d.toFixed(1);                // '123.5'
d.toFixed(2);                // '123.46'
d.toFixed(3);                // '123.456'
```
```javascript
a.toPrecision(1);            // '2'
a.toPrecision(4);            // '2.000'
c.toPrecision();             // '3.141592653589793'
c.toPrecision(0);            // Kaboom!
c.toPrecision(1);            // '3'
c.toPrecision(2);            // '3.1'
c.toPrecision(3);            // '3.14'
d.toPrecision();             // '123.456'
d.toPrecision(0);            // Kaboom!
d.toPrecision(1);            // '1e+2'
d.toPrecision(2);            // '1.2e+2'
d.toPrecision(3);            // '123'
```
```javascript
c.toExponential(0);          // '3e+0'
c.toExponential(1);          // '3.1e+0'
c.toExponential(2);          // '3.14e+0'
d.toExponential(0);          // '1e+2'
d.toExponential(1);          // '1.2e+2'
d.toExponential(2);          // '1.23e+2'
```
```javascript
Number(true);                // 1
Number(false);               // 0
Number(null);                // 0
Number(b);                   // 3
Number(d);                   // 123.456
Number(` ${a} `);            // 2
Number("1,2");               // NaN
Number("1 2");               // NaN
Number("a");                 // NaN
```
```javascript
Number.isInteger(1);         // true
Number.isInteger(2.5);       // false
Number.isInteger(null);      // false
Number.MAX_VALUE;            // 1.7976931348623157e+308
Number.MIN_VALUE;            // 5e-324
Number.POSITIVE_INFINITY;    // Infinity
1/0;                         // Infinity
Number.NEGATIVE_INFINITY;    // -Infinity
-1/0;                        // -Infinity
```
<br/>

### Functions

```javascript
const n = [1,2,3];
```
```javascript
let a = (x,y) => { return x + y };
let b = (x,y) => { return x - y };
let c = (x,y) => { return x * y };
let d = (x,y) => { return x / y };

a(2,3);                      // 5
b(2,3);                      // -1
c(2,3);                      // 6
d(2,3);                      // 0.6666666666666666
```

```javascript

let x = 0;
for (let i = 0, max = n.length; i < max; i++) {
    x += n[i];
};
x;                           // 6
```

```javascript

x = 0;
n.forEach(function(y){
    x += y;
});
x;                           // 6
```

```javascript

const m = { p: 'p', q: 'q' };
for (let i in m) {
    if (m.hasOwnProperty(i)) console.log(`${i} = ${m[i]}`);
};
// p = p
// q = q
```

```javascript
const f = x => {
    if (x === 2) return 'a';
    else if (x === 1) return 'b';
    else return 'c';
};
f(2);                        // 'a'
f(1);                        // 'b'
f(0);                        // 'c'
```

```javascript
function g(x) {
  switch(x) {
      case 1: return 'a'; break;
      case 0: return 'b'; break;
      default: return 'c';
  }
};
g(1);                        // 'a'
g(0);                        // 'b'
g(-1);                       // 'c'
```

```javascript
function h(x,y) {
    switch(true) {
        case x * y > 4: return 'a'; break;
        case x * y > 2: return 'b'; break;
        default: return 'c';
    }
};
h(2,3);                      // 'a'
h(2,2);                      // 'b'
h(1,0);                      // 'c'
```

```javascript
function s(x,y) {
    if (y) console.log(`x: ${x}, y: ${y}`);
    else console.log(`x: ${x}`);
};
s('a','b');                  // x: a, y: b
s('a');                      // x: a
```

```javascript
let t = x => x >= 0
t(3)                         // true
t(-1)                        // false
let u = (x,y) => x / y       
u(8,2)                       // 4
u(1,3)                       // 0.3333333333333333
```

```javascript
const v = x => (x < 10) ? true : false;
v(5);                         // true
v(15);                        // false
```

```javascript
function w() {
    try {
        throw 'e';                  
    } catch (e) {
        console.log(e);
    }
};
w();                         // 'e'
```

```javascript
const o = (x) => {
    try {
        p();
    }
    catch(e) {
        console.log(`${x} failed: ${e}`);
    }
};
function p() {
    var x = Math.random() <= 0.1;
    if (x) {
        throw 'error';
    }
};
for (let i = 0; i < 10; i++) {
    o(i);
};
                             // NOTE! Different each time due to non-deterministic function
                             // 2 failed: error
                             // 8 failed: error
```

<br/>

### Arrays

```javascript
const m = ['a','b','c','d'];
const n = [1,2,3];
const s = 'A;b;c';
```

```javascript
m;                           // ['a','b','c','d']
m.length;                    // 4
m[0];                        // 'a'
m[1];                        // 'b'
m[4];                        // undefined
m[m.length - 1];             // 'd'
m[m.length - 2];             // 'c'
m.slice(1);                  // ['b','c','d']
m.slice(0,1);                // ['a']
m;                           // ['a','b','c','d']
```

```javascript
m.push('e');                 // 5
m;                           // ['a','b','c','d','e']
m.unshift(1);                // 6
m;                           // [1,'a','b','c','d','e']
```

```javascript
m.pop();                     // 'e'
m;                           // [1,'a','b','c','d']
m.splice(3);                 // ['c','d']
m;                           // [1,'a','b']
m.splice(0,2);               // [1,'a']
m;                           // ['b']
```

```javascript
m.length = 0;
m;                           // []
```

```javascript
m[1] = 'b';                   
m[2] = 'c';
m.length;                    // 3
m.length = 2;
m[2];                        // undefined
m[1];                        // b
delete m[1];
m.length;                    // 2
m;                           // [ <2 empty items> ]
```

```javascript
const f = (x) => [...x];
f('ab');                     // [ 'a', 'b' ]
```

```javascript
const y = ['a', 1];
const [a, b] = y;
a;                           // 'a'
b;                           // 1
```

```javascript
const [a, b] = ['a', 1];
a;                           // 'a'
b;                           // 1
```

```javascript
const a = ['a'];
const b = ['b'];
const c = [...'ab'];
[...a, ...b];                // ['a','b']
c;                           // ['a','b']
```

```javascript
const f = (x) => x === 2;
const g = (x) => x === 5;
n.findIndex(f);              // 1
n.findIndex(g);              // -1
```

```javascript
n.filter(x => x > 1);        // [2,3]
n.filter(x => x < 1);        // []
```

```javascript
n.find(x => x === 1);        // 1
n.find(x => x === 0);        // undefined
```

```javascript
n.reverse();                 // [3,2,1]
```

```javascript
n.shift;                     // 3
[].shift();                  // undefined
```

```javascript
n.every(x => x > 0);         // true
n.every(x => x > 1);         // false
n.includes(1);               // true
n.includes(4);               // false
```

```javascript
n.sort();                    // [1,2,3]
n;                           // [1,2,3]
```

```javascript
function f(a,b) {
    if (a < b) return 1;
    if (b < a) return -1;
    else return 0;
};
n.sort(f);                   // [3,2,1]
n;                           // [3,2,1]
```

```javascript
n.push('a');
n.push('b');
n.push(true);
n.push(false);
function f(x,y) {
    if (x === y) return 0;
    if (typeof x === typeof y) return x < y ? -1 : 1;
    return typeof x < typeof y ? -1 : 1;
}
n;                           // [ 3, 2, 1, 'a','b' ,true ,false ]
n.sort(f);                   // [ false, true,1 ,2 ,3 ,'a' ,'b' ]
n;                           // [ false, true,1 ,2 ,3 ,'a' ,'b' ]
```

```javascript
Array.of(1);                 // [1]
Array.of(1, 2, 3);           // [1,2,3]
```

```javascript
'123'.split('');             // ['1','2','3']
'123'.split('-');            // ['123']
'1-23'.split('-');           // ['1','23']
```

```javascript
const m = s.split(';');
m.map(m => m.toUpperCase()); // A
                             // B
                             // C
m.map(m => m.toLowerCase()); // a
                             // b
                             // c
```

```javascript
n.join('|');                 // 1|2|3
```

```javascript
a = ['a'];
b = [2];
a.concat(b, false, 3);       // [ 'a', 2, false, 3 ]
```

```javascript
const f = x => {
    let s = '';
    x.forEach((y) => {
        s += `${y} `;
    })
    return s;
};
f([1,2,3]);                  // '1 2 3'
```
<br/>

### Math Library

```javascript
Math.trunc(1);               // 1
Math.trunc(1.4);             // 1
```

```javascript
Math.round(1.4);             // 1
Math.round(1.5);             // 2
Math.floor(1.5);             // 1
Math.ceil(1.4);              // 2
Math.round(null);            // 0
Math.floor(null);            // 0
Math.ceil(null);             // 0
```

```javascript
Math.abs(2);                 // 2
Math.abs(-2);                // 2
Math.pow(2,3);               // 8
Math.sqrt(4);                // 2
Math.sqrt(5);                // 2.23606797749979
Math.cbrt(8);                // 2
Math.cbrt(9);                // 2.080083823051904
```

```javascript
Math.min(-1,1,2);             // -1
Math.max(-1,1,2);             // 2
const a = [-1,1,2];
Math.min(a);                 // NaN
Math.max(a);                 // NaN
Math.min(...x);              // -1
Math.max(...x);              // 2
```

```javascript
Math.exp(2);                 // 7.38905609893065
Math.log(2);                 // 0.6931471805599453
Math.log10(100);             // 2
Math.log2(4);                // 2
```

```javascript
Math.sign(2);                // 1
Math.sign(-3);               // -1
```

```javascript
Math.random();               // 0.21371612513099092
Math.random();               // 0.27317142827413443      
Math.random();               // 0.9137994771416735
```
<br/>

### JSON

```javascript
const x = JSON.parse("\{\"a\":\"1\",\"b\":\"2\",\"c\":{\"d\":\"3\"}}");
x.a;                         // 1
x.b;                         // 2
x.c.d                        // 3
```

```javascript
const x = {
    a: "1",
    b: "2",
    c: {
        d: "3"
    }
};
JSON.stringify(x);           // {"a":"1","b":"2","c":{"d":"3"}}
```

```javascript
const f = x => {
    let s = ""
    x.forEach((y) => {
        s += `${y.a}:${y.b};`
    })
    return s;
};
const x = { a:"1", b:"2" };
const y = { a:"3", b:"4" };
f([x,y]);                    // 1:2 3:4
```

<br/>

## Arrays

```javascript
const n1 = [1,2]
const n2 = [3,4]
console.log(n1.concat(n2))   // [ 1, 2, 3, 4 ]
```

```javascript
const n1 = [1,2,3,4,5];
console.log(n1.copyWithin(0, 3, 4)); // [ 4, 2, 3, 4, 5 ]
console.log(n1.copyWithin(1, 3));    // [ 4, 4, 5, 4, 5 ]

```

```javascript
const n1 = [10,20];
const i1 = n1.entries();
console.log(i1.next().value);   // [ 0, 10 ]
console.log(i1.next().value);   // [ 1, 20 ]
```

```javascript
const above = (value) => value < 3;
const n1 = [1, 2];
console.log(n1.every(above));   // true
```

```javascript
const n1 = [1, 2, 3, 4];        
console.log(n1.fill(0, 2, 4));   // [ 1, 2, 0, 0 ]
console.log(n1.fill(5, 1));      // [ 1, 5, 5, 5 ]
console.log(n1.fill(6));         // [ 6, 6, 6, 6 ]
```

```javascript
const n1 = [1,2,3];
const result = console.log(n1.filter(x => x > 1))   // [ 2, 3 ]
```

```javascript
const n1 = [1, 2, 3];
console.log(n1.find(x => x === 1))   // 1
console.log(n1.find(x => x > 1))     // 2 (1st instance)
```

```javascript
const n1 = [4,5,6]
const condition = (x) => x > 4
console.log(n1.findIndex(condition))    // 1 (position 2 first number bigger than 4)
```

```javascript
const n1 = [0, 1, 2, [[[3, 4]]]]  
console.log(n1.flat())             // [ 0, 1, 2, [ [ 3, 4 ] ] ]
console.log(n1.flat(2))            // [ 0, 1, 2, [ 3, 4 ] ]
console.log(n1.flat(3))            // [ 0, 1, 2, 3, 4 ]
```

```javascript
const n1 = [1,2,3];
n1.forEach(x => console.log(x))    // 1
                                   // 2
                                   // 3
```

```javascript
console.log(Array.from('abc'))                      // [ 'a', 'b', 'c' ]
console.log(Array.from([1, 2, 3], x => x ** 2))     // [ 1, 4, 9 ]
```

```javascript
const n1 = [1, 2, 3]
console.log(n1.includes(2))   // true
console.log(n1.includes(4))   // false
```

```javascript
const n1 = [10, 20, 30]

console.log(n1.indexOf(10))       // 0
console.log(n1.indexOf(40))       // -1
console.log(n1.indexOf(20, 1))    // 1
console.log(n1.indexOf(20, 2))    // -1
```


```javascript
Array.isArray([1, 2])       // true
Array.isArray({x: 1})       // false
Array.isArray('test')       // false
Array.isArray(undefined)    // false
```

```javascript
const n1 = [1, 2, 3]        
console.log(n1.join())      // 1,2,3
console.log(n1.join(''))    // 123
console.log(n1.join('-'))   // 1-2-3
```

```javascript
const n1 = ['a','b','c']
const iterator = n1.keys()

for (const key of iterator) {       // 0 a
  console.log(key, n1[key])         // 1 b
}                                   // 2 c
```

```javascript
const n1 = ['a','b','a','c']
console.log(n1.lastIndexOf('a'))    // 2
console.log(n1.lastIndexOf('b'))    // 1
```

```javascript
const n1 = [1,2,3]
console.log(n1.map(x => x ** 2))    // 1 4 9
```

```javascript
Array.of(1);         // [1]
Array.of(1, 2, 3);   // [1, 2, 3]
Array.of(undefined); // [undefined]
```

```javascript
const n1 = ['a','b','c'];
console.log(n1.pop())  // c
console.log(n1)        // [a,b]
```

```javascript
const n1 = [1, 2, 3]
const r = (x, y) => x + y
console.log(n1.reduce(r))       // 6
console.log(n1.reduce(r, 5))    // 1
```

```javascript
const n1 = [[0, 1], [2, 3]].reduceRight(
  (x, y) => x.concat(y)
)

console.log(n1)   // [2, 3, 0, 1] 
```

```javascript
console.log([1, 2, 3].reverse())   // [3,2,1]
```

```javascript
const n1 = [1, 2, 3];
console.log(n1.shift())   // 1
console.log(n1)           // [2, 3]
```

```javascript
const animals = ['a', 'b', 'c', 'd', 'e'];
console.log(animals.slice(2))                // ["c", "d", "e"] 
console.log(animals.slice(2, 4))             // ["c", "d"] 
console.log(animals.slice(1, 10))            // ["b", "c", "d", "e"] 
```

```javascript
const even = x => x % 2 === 0;
console.log([1, 2, 3, 4, 5].some(even))      // true
```

```javascript
console.log([3, 2, 1].sort())     // [1, 2, 3]
```

```javascript
const n1 = ['a', 'c', 'd']
n1.splice(1, 0, 'b')
console.log(n1)            // ["a", "b", "c", "d"]
n1.splice(100, 1, 'e')
console.log(n1)            // ["a", "b", "c", "d", "e"] 
```

```javascript
console.log([1, 2, 'a', 'b'].toString())   // "1,2,a,b" 
```

```javascript
const n1 = [1, 2, 3]
console.log(n1.unshift(4, 5))
console.log(n1)                 // [4, 5, 1, 2, 3] 
```

```javascript
const n1 = ['a', 'b', 'c'];

for (const value of n1.values()) {
  console.log(value)                 // a b c
}

for (const value of n1.keys()) {
  console.log(value)                // 1 2 3
}
```


## Some Useful Resources
- [TypeScript Documentation](https://www.typescriptlang.org/docs/)
- [How To Work With TypeScript in Visual Studio Code](https://www.digitalocean.com/community/tutorials/how-to-work-with-typescript-in-visual-studio-code)
- [TypeScript For Beginners](https://levelup.gitconnected.com/typescript-for-beginners-97b568d3e110)
- [Classes](https://javascript.info/classes)
  - [Class basic syntax](https://javascript.info/class)
  - [Class inheritance](https://javascript.info/class-inheritance)
  - [Static properties and methods](https://javascript.info/static-properties-methods)
  - [Private and protected properties and methods](https://javascript.info/private-protected-properties-methods)
  - [Extending built-in classes](https://javascript.info/extend-natives)
  - [Class checking: "instanceof"](https://javascript.info/instanceof)
  - [Mixins](https://javascript.info/mixins)
 - [Factory Functions in ES6](https://medium.com/javascript-scene/javascript-factory-functions-with-es6-4d224591a8b1)
 
 ## Init TypeScript Libraries
- [Tutorial](https://github.com/georgemarklow/georgemarklow/blob/main/notes/typescript-starter.md)
- [Simple setup for your next TypeScript project](https://itnext.io/simple-setup-for-your-typescript-project-d96f66113b41)
- [How To Set Up a New TypeScript Project from Scratch](https://www.digitalocean.com/community/tutorials/typescript-new-project)
- [Creating a TypeScript library with a minimal setup](https://michalzalecki.com/creating-typescript-library-with-a-minimal-setup/)
- [Starter kit with zero-config for building a library in TypeScript](https://github.com/alexjoverm/typescript-library-starter)
- [TypeScript Boilerplate](https://github.com/VitorLuizC/typescript-library-boilerplate)
- [Start a New TypeScript Project](https://www.typescriptlang.org/docs/bootstrap)
- [TypeScript Node Starter](https://github.com/microsoft/TypeScript-Node-Starter)
- [TypeScript Starter](https://github.com/bitjson/typescript-starter)
- [The fast and easy way to create a TypeScript library](https://carlosroso.com/the-fast-and-easy-way-to-create-a-typescript-library/)
- [How to create your own Typescript library](https://aganglada.com/blog/how-to-create-your-own-typescript-library)
- [Publishing a TypeScript Library](https://medium.com/openmindonline/js-monday-17-publishing-a-typescript-library-59dd8200f80d)
- [How to use ESLint with TypeScript](https://khalilstemmler.com/blogs/typescript/eslint-for-typescript/)

## Best Practices
- [34 JavaScript Optimization Techniques to Know in 2021](https://js.plainenglish.io/34-javascript-optimization-techniques-to-know-in-2021-d561afdf73c3)
- [JavaScript Tips, Tricks, and Best Practices](https://medium.com/javascript-in-plain-english/common-hacks-in-javascript-5d72a6fcdac)

## Unit Testing
- [List to handle edge cases for Math js functions](http://es5.github.io/#x15.8.2.13)

## Useful links
- [Please Stop Using JS Classes](https://everyday.codes/javascript/please-stop-using-classes-in-javascript/)
- [Javascript Module Pattern](https://medium.com/technofunnel/data-hiding-with-javascript-module-pattern-62b71520bddd)
- [Master the JavaScript Interview: What is a Pure Function?](https://medium.com/javascript-scene/master-the-javascript-interview-what-is-a-pure-function-d1c076bec976)
- [Inheritance and the prototype chain](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Inheritance_and_the_prototype_chain)
- [Async Arrow Functions](https://stackoverflow.com/questions/42964102/syntax-for-async-arrow-function)
- [Waiting on Multiple Promises](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/Promise/all)
- [A simple guide to help you understand closures in JavaScript](https://medium.com/@prashantramnyc/javascript-closures-simplified-d0d23fa06ba4)
- [Understand Closure in Javascript](https://medium.com/tensult/understand-closure-in-javascript-ebba46385ecf)
- [Learn JavaScript Closures with Code Examples](https://www.freecodecamp.org/news/lets-learn-javascript-closures-66feb44f6a44/)
- [Understanding Null, Undefined and Nan](https://codeburst.io/understanding-null-undefined-and-nan-b603cb74b44c)
- [5 JavaScript Projects You Should Build As a Front-End Developer](https://medium.com/javascript-in-plain-english/5-javascript-projects-you-should-build-as-a-front-end-developer-57318b710344)
- [9 Extremely Powerful JavaScript Hacks](https://medium.com/javascript-in-plain-english/9-extremely-powerful-javascript-hacks-eed8ed11af5)
- [10 JavaScript One-liners You Have Got to Add Your Arsenal as a Developer](https://medium.com/dailyjs/10-javascript-oneliners-you-have-got-to-add-your-arsenal-as-a-developer-b733cbb973b2)
- [20 JavaScript Shorthand Techniques that will save your time](https://medium.com/javascript-in-plain-english/20-javascript-shorthand-techniques-that-will-save-your-time-f1671aab405f)
- [4 Practical Use Cases of Using filter() in JavaScript](https://medium.com/javascript-in-plain-english/4-practical-use-cases-of-using-filter-in-javascript-db46e2ec83b2)
- [How To Add, Modify and Delete JavaScript Object Literal Properties](https://medium.com/javascript-in-plain-english/add-modify-and-delete-properties-from-javascript-object-7ad07e7be1bb)
- [5 Advanced JavaScript Techniques You Should Know](https://medium.com/javascript-in-plain-english/5-advanced-javascript-techniques-you-should-know-4362e26f2ca8)
- [FUNCTIONAL JAVASCRIPT: FIVE WAYS TO CALCULATE AN AVERAGE WITH ARRAY REDUCE](https://jrsinclair.com/articles/2019/five-ways-to-average-with-js-reduce/)
- [JavaScript ES6 Modules Explained With Examples](https://medium.com/javascript-in-plain-english/javascript-es6-modules-explained-with-examples-3a85e693d56e)
- [24 Modern ES6 Code Snippets to Solve Practical JavaScript Problems](https://medium.com/swlh/24-modern-es6-code-snippets-to-solve-practical-js-problems-3609f301859e)
- [JavaScript Decorators From Scratch](https://blog.bitsrc.io/javascript-decorators-from-scratch-c4cfd6c33d70)
- [15 Rules For Writing Clean JavaScript](https://medium.com/javascript-in-plain-english/15-rules-for-writing-clean-javascript-8e2b2b426515)
- [The Difference Between The Spread Operator and The Rest Operator](https://medium.com/javascript-in-plain-english/the-difference-between-the-spread-operator-and-the-rest-operator-45c271393e5d)
- [Why Factories are better than Classes in JavaScript](https://medium.com/javascript-in-plain-english/why-factories-are-better-than-classes-in-javascript-1248b600b6d4)
- [Think twice before using Array.reduce()](https://blog.bitsrc.io/array-reduce-think-twice-before-using-it-c00f22ec9273)
- [JavaScript Basics: How to create a Dictionary with Key/Value pairs](https://pietschsoft.com/post/2015/09/05/javascript-basics-how-to-create-a-dictionary-with-keyvalue-pairs)
- [6 Tips to Improve Your Conditional Statements for Better Readability](https://medium.com/javascript-in-plain-english/6-tips-to-improve-your-conditional-statements-for-better-readability-56256c5a5245)
- [The Problem with Testing for NaN in JavaScript](http://adripofjavascript.com/blog/drips/the-problem-with-testing-for-nan-in-javascript.html)
- [NaN, isNaN() & Number.isNaN()](https://www.codementor.io/@diegopalacios/nan-isnan-number-isnan-1agz7vzs08)
- [15 Typescript Mistakes To Avoid](https://blog.softwaremill.com/typescript-mistakes-to-avoid-d3ab240c90eb)
- [Which type of loop is fastest in JavaScript?](https://medium.com/javascript-in-plain-english/which-type-of-loop-is-fastest-in-javascript-ec834a0f21b9)
- [Accuracy of JavaScript Time](https://johnresig.com/blog/accuracy-of-javascript-time/)
- [5 Advanced TypeScript Tips To Make You a Better Programmer](https://levelup.gitconnected.com/5-advanced-typescript-tips-to-make-you-a-better-programmer-bd4070aa2ab4)
