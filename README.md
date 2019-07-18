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

## Encapsulation

Encapsulation is a mechanism of wrapping the data (variables) and code acting on the data (methods) together as a single unit. In encapsulation, the variables of a class will be hidden from other classes, and can be accessed only through the methods of their current class. Therefore, it is also known as data hiding.

```csharp
class Student  
    {
        private string Name;        
        public string getName()
        {
            return Name;
        }
    }
```

## Inheritance

Inheritance is a process in which one object acquires all the properties and behaviors of its parent object.

```csharp
public class Man  
{
    public string name { get; set; }
    public int age { get; set; }
}  
public class Employee : Man
{
    public string Department { get; set; }
    public int EmployeeID { get; set; }
}
```

## Polymorphism
Polymorphism refers to the ability of a variable, object or function to take on multiple forms.

### Static Polymorphism - static binding or early binding.
- Function overloading
- Operator overloading

#### Function overloading

You can have multiple definitions for the same function name in the same scope. The definition of the function must differ from each other by the types and/or the number of arguments in the argument list. You cannot overload function declarations that differ only by return type.


##### Member Overloading

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
}

public class Program  
{  
    public static void Main()  
    {  
       string stringaddme = 5;
        int intaddme = 5;
        Console.WriteLine(Calculate.Add(addme));
        Console.WriteLine(Calculate.Add(intaddme));
    }  
}
```

##### Method Overloading

```csharp
class Calculate
{
    public static int add(int a,int b){  
        return a + b;  
    }  
    public static int add(int a, int b, int c)  
    {  
        return a + b + c;  
    }
}
public class Program  
{  
    public static void Main()  
    {  
        Console.WriteLine(Calculate.add(12, 23));  
        Console.WriteLine(Calculate.add(12, 23, 25));  
    }  
}  
```

#### Operator overloading

Overloaded operators are functions with special names the keyword operator followed by the symbol for the operator being defined.

```csharp
class Square {
      private double side;   

      public double getArea() {
         return side * side;
      }
      
      // Overload + operator to add two Box objects.
      public static Square operator+ (Square a, Square b) {
         Square square = new Square();
         square.side = a.side + b.side;
         return square;
      }
   }
```

### Dynamic Overloading - dynamic binding or late binding

Runtime polymorphism in achieved by method overriding

```csharp
abstract class Shape {
      public virtual int area();
      }
      
class Rectangle:  Shape {
      private int length;
      private int width;
      
      public Rectangle( int a = 0, int b = 0) {
         length = a;
         width = b;
      }
      public override int area () { 
         Console.WriteLine("Rectangle class area :");
         return (width * length); 
      }
   }
 
class Square:  Shape {
      private int side;
      
      public Square( int a = 0) {
         side = a;
      }
      public override int area () { 
         Console.WriteLine("Square class area :");
         return (side * side); 
      }
   }
```

## Abstract 

C# allows you to create abstract classes that are used to provide partial class implementation of an interface. Implementation is completed when a derived class inherits from it. Abstract classes contain abstract methods, which are implemented by the derived class.

```csharp
abstract class Shape {
      public abstract int area();
      }
      
class Rectangle:  Shape {
      private int length;
      private int width;
      
      public Rectangle( int a = 0, int b = 0) {
         length = a;
         width = b;
      }
      public override int area () { 
         Console.WriteLine("Rectangle class area :");
         return (width * length); 
      }
   }
 
class Square:  Shape {
      private int side;
      
      public Square( int a = 0) {
         side = a;
      }
      public override int area () { 
         Console.WriteLine("Square class area :");
         return (side * side); 
      }
   }
```

## Interface
Interface in C# is a blueprint of a class. It is like abstract class because all the methods which are declared inside the interface are abstract methods. It cannot have method body and cannot be instantiated.

It is used to achieve multiple inheritance which can't be achieved by class. It is used to achieve fully abstraction because it cannot have method body.

```csharp

public interface class Shape 
{
    int area();
}
      
class Rectangle : Shape 
{
    public int area () { 
         Console.WriteLine("Rectangle class area :");
         return (width * length); 
      }
}
 
class Square : Shape 
{
    public int area () { 
         Console.WriteLine("Square class area :");
         return (side * side); 
      }
}
```

## Association, Composition & Aggregation

### Association in C#
The association defines the relationship between an object in C#. An a one-to-one, one-to-many, many-to-one and many-to-many relationship can be defined between objects.

For example, An Employee can be associated with multiple projects, whereas a project can have more than one employee.

### Composition in C#
Under Composition, if the parent object is deleted, then the child object also loses its status.

The composition is a special type of Aggregation and gives a part-of relationship.

For example, A Car has an engine. If the car is destroyed, the engine is destroyed as well.

### Aggregation in C#
Aggregation is a direct relation between objects in C#. It is the relationship between objects.

For example, Employee and Department.

An Employee is associated with a single Department, whereas a Department can have more than one employee
