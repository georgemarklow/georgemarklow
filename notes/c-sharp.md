# C#

## Contents

- [Strings](https://github.com/georgemarklow/georgemarklow/blob/main/notes/c-sharp.md#strings)

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

## Arrays

## StringBuilder

## Stack

## Queue

## Dictionary

## List

## SortedList

## Hashset
