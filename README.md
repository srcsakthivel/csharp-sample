# csharp-sample

## Class
A class is a blueprint or template or set of instructions to build a specific type of object. Every object is built from a class.

```csharp
using System;

public class Man
{
    public string Name {get; set;}
    public int Age {get; set;}
}
```

## Object
An object can be defined as an instance of a class.

```csharp
using System;

public class Program
{
    Man man = new Man();
}
```

## Inheritance
Inheritance is an OOPS concept in which one object acquires the properties and behaviors of the parent object. It’s creating a parent-child relationship between two classes.

Man -> Base Class
Employee -> Derived Class 

```csharp
using System;

public class Man
{
    public string Name {get; set;}
    public int Age {get; set;}
}

public class Employee : Man
{
    public string Role {get; set;}
    public int Salary {get; set;}
}
```

## Polymorphism
Polymorphism refers to the ability of a variable, object or function to take on multiple forms.

```csharp
class Calculate
{
    public static int Add(int number)
    {
        Console.WriteLine("Integer Add");
        return number + number;
    }
    
    public static string Add(string text)
    {
        Console.WriteLine("String Add");
        return text + text;
    }
    
    static void Main(string[] args)
`   {
        string stringaddme = 5;
        int intaddme = 5;
        Console.WriteLine(Calculate.Add(addme));
        Console.WriteLine(Calculate.Add(intaddme));
    }
}
```
