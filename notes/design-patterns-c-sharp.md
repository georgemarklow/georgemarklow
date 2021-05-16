# Design Patterns in C#

## Resources
- [The Catalog of C# Examples](https://refactoring.guru/design-patterns/csharp)
- [The Catalog of TypeScript Examples](https://refactoring.guru/design-patterns/typescript)

<br/>

## Contents

- [Abstract Factory](https://github.com/georgemarklow/georgemarklow/blob/main/notes/design-patterns-c-sharp.md#abstract-factory)

<br/>

## Abstract Factory

### Benefits:
- Possible to interchange the concrete classes without changing the client code even at runtime.

### Drawback:
- Extra complexity and writing the code during the initial stages.

<br/>

```csharp
    class Program
    {
        static void Main(string[] args)
        {
            F fa = new FA();

            I1 o1 = fa.m1();
            o1.F1();
            o1.F2();

            I2 o2 = fa.m2();
            o2.F3();
            o2.F4();

            F fb = new FB();

            I1 o3 = fb.m1();
            o3.F1();
            o3.F2();

            I2 o4 = fb.m2();
            o4.F3();
            o4.F4();

            Console.ReadLine();
        }
    }

    public interface F
    {
        I1 m1();
        I2 m2();
    }

    public interface I1
    {
        void F1();
        void F2();
    }

    public interface I2
    {
        void F3();
        void F4();
    }

    public class FA : F
    {
        public I1 m1()
        {
            return new C1();
        }

        public I2 m2()
        {
            return new C2();
        }
    }

    public class FB : F
    {
        public I1 m1()
        {
            return new C3();
        }

        public I2 m2()
        {
            return new C4();
        }
    }

    class C1 : I1
    {
        public void F1()
        {
            Console.WriteLine("C1:F1");
        }
        public void F2()
        {
            Console.WriteLine("C1:F2");
        }
    }

    class C2 : I2
    {
        public void F3()
        {
            Console.WriteLine("C2:F3");
        }
        public void F4()
        {
            Console.WriteLine("C2:F4");
        }
    }

    class C3 : I1
    {
        public void F1()
        {
            Console.WriteLine("C3:F1");
        }
        public void F2()
        {
            Console.WriteLine("C3:F2");
        }
    }

    class C4 : I2
    {
        public void F3()
        {
            Console.WriteLine("C4:F3");
        }
        public void F4()
        {
            Console.WriteLine("C4:F4");
        }
    }
```
