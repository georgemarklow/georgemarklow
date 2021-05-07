# Solid

## Content
- [Single Responsibility Principle]()
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
