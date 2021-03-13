# Javascript

## JavaScript Warm-Up Drill in Node

<img width="600" alt="Screenshot 2021-03-08 at 9 15 03 pm" src="https://user-images.githubusercontent.com/11710404/110382832-5d3f4300-8053-11eb-8307-b783495f9cfa.png">

### Contents
- [Console Basics](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#console-basics)
- [Strings](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#strings)
- [Numbers](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#numbers)
- [Functions](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#functions)
- [Arrays](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#arrays)
- [Math Library](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#math-library)
- [JSON](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#json)
- [Promises](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#promises)
- [Async/Await](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#asyncawait)
- [Closures](https://github.com/georgemarklow/georgemarklow/blob/main/notes/javascript.md#closures)

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
const s = 'Abc'     // undefined
const t = ' def '   // undefined
s                   // 'Abc'
```
```javascript
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

let m = { p: 'p', q: 'q' };
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
x;                           // 6
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
c;                           // [ 'a', 'b' ]
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
function f(z) {
    let x = 0
    m.forEach(y => {
        x += y;
    })
    return Math.round(x / z.length);
};
f(n);                        // 2
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

### Promises

```javascript
setTimeout(() => {
    console.log('s');        // [...] s
}, 1000);
```

```javascript
const f = x => {
    return new Promise(y => {
        setTimeout(() => {   
            y()         
        }, x);
    });
};

f(1000).then(() => {
    console.log('s');        // [...] s
});
```
```javascript
const f = x => {
    return new Promise(y => {
        y(x === "a");
    });
};

console.log('1');

f(1000).then(() => {
    console.log('2');
});

console.log('3');
                             // 1
                             // 3
                             // 2
                             
```
```javascript

const f = () => {
    const x = {
        a: 1,
        b: 2
    };
    return new Promise(y => {
        setTimeout(() => {
            y(x);
        }, 3000);
    });
};

f().then(x => {
    console.log(x);          // [...] { a: 1, b: 2 }
});
```

```javascript
const g = x => {
    return new Promise(y => {
        setTimeout(() => {
            y();
        }, x);
    });
};

const f = () => {
     g(() => { console.log('a') });
    .then(() => { console.log('b') });
    .catch(() => { console.log('c') });
};
f();
```
<br/>

### Async/Await

```javascript
const f = async (x) => { 
    return Promise.resolve(x);
};
f('s').then(console.log);    // Promise { <pending> }
                             // s
```
```javascript
const f = async (x) => { 
    return Promise.resolve(x);
};
f('s').then(console.log);    // Promise { <pending> }
                             // s
```
```javascript
async function f(s,t) {
    let promise = new Promise((resolve, reject) => {
        setTimeout(() => resolve(s), t)
    });
    console.log(await promise);
}
f('s', 3000);                // Promise { <pending> }
                             // s
```
```javascript
const p1 = 1;
const p2 = Promise.resolve(2);
const p3 = new Promise((resolve, reject) => {
    setTimeout(resolve, 1000, 3);
});
Promise.all([p1, p2, p3]).then((values) => {
    console.log(values);
});
// [ 1, 2, 3 ]
```
<br/>

### Closures

```javascript
function f() {
    let y = 2;
    function g() { 
        var x = 1; 
        console.log(`${x} ${y}`);
        x++;
        y++;
    }
    return g;
}
var a = f(); 
var b = f(); 
a();                         // 1 2
a();                         // 1 3
b();                         // 1 2
```

```javascript
function f1() {
    let x = 'b'
    function f2() {
        console.log('a')
        console.log(x)
    }
    x = 'c'
    return f2
}
var f = f1();
f()                          // a
                             // c
                             
```

```javascript

function f(x) {
    return function(y) { return x * y }
}
var g = f(1)
var h = f(2)
g(2)                         // 2 (1 * 2)
h(2)                         // 4 (2 * 2)

```

```javascript

var f = (function() {
    var a = 1
    function times(x) { a *= x }
    return {
        p: function() { times(2) },
        q: function() { times(0.5) },
        r: function() { return a }
    }
})()
console.log(f.r())           // 1
f.p()
console.log(f.r())           // 2
f.q()
f.q()
console.log(f.r())           // 0.5
```

## Summary
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
