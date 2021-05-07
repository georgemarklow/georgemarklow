# Solid

## Content
- [Single Responsibility Principle](https://github.com/georgemarklow/georgemarklow/blob/main/notes/solid.md#single-responsibility-principle)
- []()
- []()
- []()
- []()

## Single Responsibility Principle

### Bad

```csharp
    public class Employee
    {
        public int Id { get; set; }
        public string Name { get; set; }

        public bool Insert(Employee em)
        {
            return true;
        }

        public void GenerateReport(Employee em)
        {

        }
    }
```

### Good

```csharp
    public class Employee
    {
        public int Id { get; set; }
        public string Name { get; set; }

        public bool Insert(Employee em)
        {
            return true;
        }
    }

    public class EmployeeGeneration
    {
        public void GenerateReport(Employee em)
        {

        }
    }
```
