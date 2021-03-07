# C#

## Contents

- [Strings](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#strings)
- [Arrays](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#arrays)
- [Dictionary](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#dictionary)
- [Stack](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#stack)
- [Queue](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#queue)
- [List](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#list)
- [SortedList](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#sortedlist)

<br/>

## Strings

### Compare
```csharp
string.Compare("a", "a")
string.Compare("a", "b")
string.Compare("b", "a");
string.Compare("A", "a");
```
### CompareTo
```csharp
var s1 = "a";               
s1.CompareTo(s1);
s1.CompareTo("a");
```
### Concat
```csharp
string.Concat("a", "b")
```
### Contains
```csharp
"abc".Contains("A")
"abc".Contains("a")
```

### StartsWith, EndsWith
```csharp
"abc".StartsWith("A")
"abc".StartsWith("a")

"abc".EndsWith("C")
"abc".EndsWith("c")
```
### Equals
```csharp
var s2 = "a";
var s3 = "b";
"a".Equals(s2);
"a".Equals(s3);
```
### Enumerator
```csharp
var charEnum = "abc".GetEnumerator();
while (charEnum.MoveNext())
    Console.WriteLine(charEnum.Current);
```
### GetHashCode
```csharp
"abc".GetHashCode()
```
### IndexOf
```csharp
"abc".IndexOf("a")
"abc".IndexOf("A")
"abc".IndexOf("d")
```

### IsNullOrEmpty
```csharp
string.IsNullOrEmpty("a")
string.IsNullOrEmpty(null)
string.IsNullOrEmpty("")
string.IsNullOrEmpty(" ")
```
### Join
```csharp
string[] s4 = { "abc", "def" };
string.Join("-", s4);
```
### Remove
```csharp
"abc".Remove(2);
"abc".Remove(1, 2);
```
### Replace
```csharp
"abc".Replace("c", "d")
```
### Split
```csharp
"a b c".Split(' ')
```
### Substring
```csharp
"abc".Substring(1)
"abc".Substring(1, 2)
```
### ToCharArray
```csharp
var chars = "abc".ToCharArray()
```
### ToUpper, ToLower
```csharp
"Abc".ToUpper()
"Abc".ToLower()
```
### Trim, TrimStart, TrimEnd
```csharp
" abc ".Trim()
" abc ".TrimStart()
" abc ".TrimEnd()
```
<br/>

## Arrays

### Initialization
```csharp
var arr1 = new int[2]
var arr2 = new int[2] { 1, 2 }
int[] arr3 = { 1, 2 }
```
### Setting Vales
```csharp
var arr = new int[] { 1, 2 };
arr[1] = 3;
arr[0]
arr[1]
```
### Multi-Dimensional Arrays
```csharp
var arr1 = new int[3, 2]
{
    { 1, 2 },
    { 3, 4 },
    { 5, 6 }
};

int[,] arr2 = { { 1, 2 }, { 3, 4 }, { 5, 6 } };

arr1[0, 0]
arr1[0, 1]
arr1[1, 0]
arr1[1, 1]
arr1[2, 0]
arr1[2, 1]
```

### Jagged Arrays
```csharp
var arr = new int[2][]
{
    new int[3]{1,2,3},
    new int[2]{4,5}
};

arr[0][0]
arr[2][0]
arr[1][1]
```

### Array of Arrays
```csharp
var arr = new int[2][][]
{
    new int[2][]
    {
        new int[3] {1,2,3},
        new int[2] {4, 5}
    },
    new int[1][]
    {
        new int[3] {7,8,9}
    }
};

arr[0][0]
arr[2][0]
arr[1][1]
```

<br/>

## Dictionary

### Initialization
```csharp
var dict1 = new Dictionary<int, string>
{
    { 1, "a" },
    { 2, "b" }
};

var dict2 = new Dictionary<int, string>();
dict2.Add(1, "a");
dict2.Add(2, "b");

IDictionary<int, string> dict3 = new Dictionary<int, string>();
dict3.Add(new KeyValuePair<int, string>(1, "a"));
dict3.Add(new KeyValuePair<int, string>(2, "b"));
```

### Accessing Elements
```csharp
var dict = new Dictionary<int, string>
{
    { 1, "a" },
    { 2, "b" }
};

dict[1];    // a
dict[2];    // b
```

### Try Accessing Values

```csharp

var dict = new Dictionary<int, string>
{
    { 1, "a" },
    { 2, "b" }
};

string value;
dict.TryGetValue(1, out value);     // True
value;                              // a

```

### Looping Through Elements
```csharp
foreach (var item in dict)
{
    Console.WriteLine($"key: {item.Key} value: {item.Value}");
}

foreach (KeyValuePair<int, string> item in dict)
{
    Console.WriteLine($"key: {item.Key} value: {item.Value}");
}

foreach (var key in dict.Keys)
{
    Console.WriteLine($"key: {key}");
}

foreach (var value in dict.Values)
{
    Console.WriteLine($"value: {value}");
}
```

### ContainsKey, Contains (Value)

```csharp

var dict = new Dictionary<int, string>
{
    { 1, "a" },
    { 2, "b" }
};

dict.ContainsKey(1);        // True
dict.ContainsKey(3);        // False
dict.ContainsValue("a");    // True
dict.ContainsValue("c");    // False

```

### Remove
```csharp

var dict = new Dictionary<int, string>
{
    { 1, "a" },
    { 2, "b" }
};

dict.Remove(1);     // True
dict.Count;         // 1

```

## StringBuilder

## Stack

### Adding Values to the Stack

```csharp

Stack<int> stack = new Stack<int>();
stack.Push(1);
stack.Push(2);
stack.Push(3);
stack.Push(4);
stack.Push(5);
    
foreach (var item in stack)
    print(item);
    
// 1
// 2
// 3
// 4
// 5

```

### Checking Stack Contents

```csharp

stack.Contains(1);                  // True
stack.Contains(10);                 // False

```

### Peek and Pop

```csharp

stack.Peek();                       // 5
stack.Count;                        // 5
stack.Pop();                        // 5
stack.Peek();                       // 4

int peekedValue;    
stack.TryPeek(out peekedValue);
peekedValue;                        // 4

int poppedValue;
stack.TryPop(out poppedValue);
poppedValue;                        // 4

```

### Clear the Stack

```csharp

stack.Clear();
stack.Count;                    // 0

```

## Queue

### Adding Items

```csharp

var queue = new Queue<string>();
queue.Enqueue("one");
queue.Enqueue("two");
queue.Enqueue("three");
queue.Count;
    
foreach (var item in queue)
    Console.WriteLine(item);
queue.Contains("one");
queue.Contains("four");

```

### Peeking and Dequeuing

```csharp

queue.Peek();
queue.Dequeue();

string peekedItem;
queue.TryPeek(out peekedItem);
peekedItem;

string dequeuedItem;
queue.TryDequeue(out dequeuedItem);
dequeuedItem;

```

### Clearing the Queue

```csharp

queue.Clear();
queue.Count;

```

## List

### Initialize

```csharp

class Person { }

List<string> list = new List<string>
{
    "one", "two", "three"
};

var people = new List<Person>
{
    new Person()
};

```

### Add Elements

```csharp

var list = new List<string>();
list.Add("one");
list.Add("two");
list.Add("three");

list.AddRange(new List<string> { "four", "five" });     // { "one", "two", "three", "four", "five" }
list.Count                                              // 5

```

### Accessing Collection

```csharp

foreach (var item in list)
    print(item);            // "one", "two", "three", "four", "five"
    
list[1]                     // "two"

for (var i = 0; i < list.Count; i++)
{
    $"index: {i} item {list[i]}";
};

//  index: 0 item one
//  index: 1 item two
//  index: 2 item three
//  index: 3 item four
//  index: 4 item five

```

### Inserting Elements

```csharp

list.Insert(1, "A");
list.InsertRange(3, new List<string> { "B", "C" });

//  one
//  A
//  two
//  B
//  C
//  three
//  four
//  five

```

### Remove Elements

```csharp

list.Remove("one");                         // True
list.RemoveAt(1);                           
list.RemoveAll(x => x.StartsWith("t"));     // 1
list.RemoveRange(1, 2);                     

//  A
//  four
//  five

list.TrueForAll(x => x.StartsWith("f"));    // False

```

## SortedList

### Adding Items and Checking the List

```csharp

var list = new SortedList<string, int>();
list.Add("one", 1);
list.Add("two", 2);
list.Add("three", 3);
list.Add("four", 4);

list["one"];
list.ContainsKey("one");
list.ContainsKey("five");
list.ContainsValue(1);
list.ContainsValue(5);

```

### Looping through the List Contents

```csharp

for (int i = 0; i < list.Count; i++)
{
    Console.WriteLine($"{list.Keys[i]} {list.Values[i]}");
}

// four 4
// one 1
// three 3
// two 2

foreach (var kvp in list)
{
    Console.WriteLine($"{kvp.Key} {kvp.Value}");
}

// four 4
// one 1
// three 3
// two 2

```

### Printing Keys and Values Directly

```csharp

foreach (string key in list.Keys)
{
    Console.WriteLine(key);
}

// four
// one
// three
// two

foreach (int value in list.Values)
{
    Console.WriteLine(value);
}

// 4
// 1
// 3
// 2

```

### Attempting to Get a Value

```csharp

int val;
if (list.TryGetValue("one", out val))
{
    Console.WriteLine(val);
}

```

### Attempting to Get a Key

```csharp

if (list.ContainsValue(6))
    Console.WriteLine(list.First(kvp => kvp.Value == 6).Key);
    
```

### Removing Items

```csharp

list.Remove("three");
list.RemoveAt(0);

foreach (var kvp in list)
{
    Console.WriteLine($"{kvp.Key} {kvp.Value}");
}

// one 1
// two 2

```

## Hashset
