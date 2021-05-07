# Solid

## Content
- [Single Responsibility Principle](https://github.com/georgemarklow/georgemarklow/blob/main/notes/solid.md#single-responsibility-principle)
- [Open/Closed Principle](https://github.com/georgemarklow/georgemarklow/blob/main/notes/solid.md#openclosed-principle)
- [Liskov Substitution Principle](https://github.com/georgemarklow/georgemarklow/blob/main/notes/solid.md#liskov-substitution-principle)
- [Interface Segregation Principle](https://github.com/georgemarklow/georgemarklow/blob/main/notes/solid.md#interface-segregation-principle)
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

## Liskov Substitution Principle

### Bad
```cshasp
    public abstract class Employee
    {
        public virtual string GetProjectDetails(int employeeId)
        {
            return "Base Project";
        }

        public virtual string GetEmployeeDetails(int employeeId)
        {
            return "Base Employee";
        }
    }

    public class PermanentEmployee : Employee
    {
        public override string GetProjectDetails(int employeeId)
        {
            return "Child project";
        }

        public override string GetEmployeeDetails(int employeeId)
        {
            return "Child employee";
        }
    }

    public class ContractEmployee : Employee
    {
        public override string GetProjectDetails(int employeeId)
        {
            return "Child project";
        }

        public override string GetEmployeeDetails(int employeeId)
        {
            throw new NotImplementedException();
        }
    }
```

### Good

```chsarp
    public abstract class Employee
    {
        public virtual string GetProjectDetails(int employeeId)
        {
            return "Base Project";
        }

        public virtual string GetEmployeeDetails(int employeeId)
        {
            return "Base Employee";
        }
    }

    public class PermanentEmployee : IEmployee, IProject
    {
        public string GetProjectDetails(int employeeId)
        {
            return "Child project";
        }

        public string GetEmployeeDetails(int employeeId)
        {
            return "Child employee";
        }
    }

    public class ContractEmployee : IProject
    {
        public string GetProjectDetails(int employeeId)
        {
            return "Child project";
        }
    }

    public interface IEmployee
    {
        string GetEmployeeDetails(int employeeId);
    }

    public interface IProject
    {
        string GetProjectDetails(int employeeId);
    }
```

## Interface Segregation Principle

### Bad

```csharp
    public interface IEmployeeDatabase
    {
        bool Add();
        bool Get();
    }
```

### Good

``` csharp
    public interface IAddOperation
    {
        bool Add();
    }

    public interface IGetOperation
    {
        bool Get();
    }
```

## Dependency Investion Principle

### Bad

```csharp
    public class Email
    {
        public void SendEmail()
        {
        }
    }

    public class Notification
    {
        private Email _email;

        public Notification()
        {
            _email = new Email();
        }

        public void PromotionalNotification()
        {
            _email.SendEmail();
        }
    }
```

### Good

``` csharp
    public interface IMessenger
    {
        void SendMessage();
    }

    public class Email : IMessenger
    {
        public void SendMessage()
        {
            // Email
        }
    }

    public class SMS : IMessenger
    {
        public void SendMessage()
        {
            // SMS
        }
    }

    public class Notification
    {
        private IMessenger _messenger;

        public Notification(IMessenger messenger)
        {
            _messenger = messenger;
        }

        public void DoNotify()
        {
            _messenger.SendMessage();
        }
    }
```
