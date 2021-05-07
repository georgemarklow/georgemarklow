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

## Open/Closed Principle

### Bad
```csharp
    public class ReportGeneration
    {
        public string ReportType { get; set; }

        public void GenerateReport(Employee em)
        {
            if (ReportType == "CRS")
            {
                // CRS...
            }

            if (ReportType == "PDF")
            {
                // PDF...
            }
        }
    }
```

### Good
```csharp
    public abstract class ReportGeneration
    {
        public virtual void GenerateReport(Employee em)
        {
            // from base
        }
    }

    public class CrystalReportGeneration : ReportGeneration
    {
        public override void GenerateReport(Employee em)
        {
            // generate crystal report
        }
    }

    public class PDFReportGeneration : ReportGeneration
    {
        public override void GenerateReport(Employee em)
        {
            // generate PDF report
        }
    }
```
