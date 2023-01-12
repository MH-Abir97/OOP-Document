
> ## Object-oriented programming is a real-world programing.Object-oriented programming is a way of developing software applications using real-world terminologies to create entities that interact with one another using objects. 


* Object-oriented programming makes applications flexible
* East to change or add new features
* Re-usable, well-structured, and easy to debug and test.

## 5 Basic building blocks to build object-oriented applications : -
* *Classes :* A Class define the structure using methods and properties/fields that resemble real-world entity.
* *Methods :* A method represents a particular behavior. It performs some action and might return information about an object, or update an object’s data.
* *Properties :* Properties hold the data temporarily during the execution of an application.
* *Objects:* Objects are instances of the class that holds different data in properties/fields and can interact with other objects.
* *Interfaces :* An interface is a contract that defines the set of rules for a particular functionality. They are used effectively with classes using OOP principles like inheritance and polymorphism to make applications more flexible.

# **Object-oriented Design Principles**

* Abstraction
* Encapsulation
* Inheritance
* Polymorphism

# Abstraction : -
Abstraction is a higher-level concept or a way of thinking. When you start designing your application from the business requirement. Abstraction is a process of identifying essential entities (classes) and their characteristics (class members) and leaving irrelevant information from the business requirement to prepare a higher-level application design.

## Types of abstraction : -

 * Data Abstraction
 * Control Abstraction

 Data Abstraction : Data abstraction refers to the concealment of data specifics

 Control Abstraction : control abstraction refers to the concealment of implementation details.

 *Abstract classes :* an abstract class is a specific type of class that can not be instantiated, which means you can not make objects from it. An abstract class aims to create a skeleton framework from which other classes can derive.

 **Characteristics of abstract class and methods :**
 * Abstract class must be Used in Abustract Keyword.
 * Abstract Class are possible in abstract method.
 * Non Abstract Class aren`t possible in abstract Method.
 * Abstract method have no method body
 * Abstract method must be declar in abstract Keyword.


 public abstract class Demo

 {

    public abstract void k1();
 }

 

 


 public abstract class Demo

    {
        public abstract void Show();

        public virtual void Print() 
        {
            Console.WriteLine("Non Abstract");
        
        }

    }

    public class Sample : Demo

    {
        public override void Show()
        {
            Console.WriteLine(" Hello Demo !!!");
        }

        public override void Print()
        {
            Console.WriteLine("Use Child Objecet");

        }
    }
    

     static void Main(string[] args)

        {
           
            Sample sample = new Sample();
            /* Call Abstract method */
            sample.Show();

           /* Call Non Abstract method */
            sample.Print();
           



        }
 
*Use the virtual keyword with a member of the base class to make it overridable, and use the override keyword in the derived class to indicate that this member of the base class is being redefined in the derived class*

class Person

{
    
    public virtual void Greet()

    {
        Console.WriteLine("Hi! I am a person.");
    }
}


class Employee : Person

{

    public override void Greet()

    {
        Console.WriteLine("Hello! I am an employee.");
    }
}


# Encapsulation :

* Encapsulation is a technique to implement abstraction in code. Create classes and their members with appropriate access modifiers to show or hide details and complexity.
* Encapsulation hides the data and implementation details show only the required members within a class, thus hiding complexity from other code. No other code needs to know about implementation detail and also can’t modify the code of the class’s data and methods.

public class Student

{

    private string _firstName;

    public string FirstName
    {
        get { return _firstName; }
        set { _firstName = value; }
    }

    private string _middleName;

    public string MiddleName
    {
        get { return _middleName; }
        set { _middleName = value; }
    }


    private string _lastName;

    public string LastName
    {
        get { return _lastName; }
        set { _lastName = value; }
    }


    public string FullName
    {
        get { return _firstName + " " + _lastName; }
    }

    public void Save() { 
        //write code to save student 
    }

    public void Subscribe(Course cs)
    {
        Verify();
            
        //write code to subscribe to a course
    }

    private void Verify()
    {
        //write code to verify student before subscribing
    }

    public void GetSubscribedCourses()
    {
        //write code to return all subscribed courses
    }


}


# There are three types of relationships in object-oriented programming based on how a class interacts with another class :- #

* Association
* Composition
  * Composition
  * Aggregation
* Inheritance

# Association :
* Association relationship is referred to as "uses a" relationship where a class uses another class to perform some operation
* Association happens between the classes where one class provides a service to another class or the class delegates some kinds of behaviors to another class.

* Association is typically implemented with a pointer or reference instance variable or as a method argument.

## Example : Association

public class Student

{

    public int StudentId { get; set; }
    public string FirstName { get; set; }
    public string MiddleName { get; set; }
    public string LastName { get; set; }
}

public class StudentRepository

{
    
    public Student GetStudent(int StudentId)
    {
        // get student by id from db here

        return new Student();
    }
    public bool Save(Student student)
    {
        // save student to db here
        Console.WriteLine("Student saved successfully");

        return true;
    }
    public bool Validate(Student student)
    {
        // get student from db to check whether the data is already exist
        Console.WriteLine("Student does not exist.");

        return true;
    }
}

![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/association.png "San Juan Mountains")


## Composition :

* Composition is referred to as "has a" relationship. Composition relationship is formed when a class has a reference to another class as an instance property.

* In the composition relationships, a class that contains the reference to another class is the parent (owner) of that child class. The child class without parent class doesn't exist.


# Example : Composition

public class Student

{

    public int StudentId { get; set; }
    public string FirstName { get; set; }
    public string MiddleName { get; set; }
    public string LastName { get; set; }
    public Address HomeAddress { get; set; }
}

public class Address

{

    public int AddressId { get; set; }
    public string Address1 { get; set; }
    public string Address2 { get; set; }
    public string City { get; set; }
    public string State { get; set; }
    public string ZipCode { get; set; }
    public string Country { get; set; }

}


![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/composition.png "San Juan Mountains")

# Important Points:

* A class (parent) contains a reference to another class (child).
* The child class doesn't exist without the parent class.
* Deleting the parent class will also delete the child class
A class can also include a reference of the id property of another class.

# Aggregation

> Aggregation is another category of "has a" relationship where a class can contain other classes as properties but those classes can exist independently.

> # Example: Aggregation

public class Student

{

    public int StudentId { get; set; }
    public string FirstName { get; set; }
    public string MiddleName { get; set; }
    public string LastName { get; set; }

    public Course EnrolledCourse { get; set; }
}

public class Course

{

    public int CourseId { get; set; }
    public string CourseName { get; set; }
    public IList Topics { get; set; }
    public DateTime StartDate { get; set; }
    public DateTime EndDate { get; set; }
}


![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/aggregation.png "San Juan Mountains")

# Important Points:

* Aggregation is another type of composition ("has a" relation).
* A class (parent) contains a reference to another class (child) where both classes can exist independently.
* A class can also include a reference of the id property of another class.

# Inheritance :-
> inheritance is another type of relationship between classes. Inheritance is a mechanism of reusing the functionalities of one class into another related class.


![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/inheritance1.png "San Juan Mountains")

> Example : Class Inheritance 

class Person

{

    public string FirstName { get; set; }
    public string LastName { get; set; }

    public string GetFullName(){ 
        return FirstName + " " + LastName;
    }
}

class Employee : Person

{

    public int EmployeeId { get; set; }
    public string CompanyName { get; set; }
    
}

# Constructors :-

> Creating an object of the derived class will first call the constructor of the base class and then the derived class. If there are multiple levels of inheritance then the constructor of the first base class will be called and then the second base class and so on.

 > Example: Constructors in Inheritance

 
class Person

{

    public Person()
    {
	    Console.WriteLine("Person Constructor");
	}
}

class Employee : Person

{

    public Employee()
    {
	    Console.WriteLine("Employee Constructor");
	}   
}

Employee emp = new Employee();


> Output :
* Person Constructor
* Employee Constructor

> # Single Inheritance

![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/inheritance2.png "San Juan Mountains")

> # Multi-level Inheritance


![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/inheritance3.png "San Juan Mountains")

> # Hierarchical Inheritance


![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/inheritance4.png "San Juan Mountains")

> # Hybrid Inheritance
![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/inheritance5.png "San Juan Mountains")

> # Multiple Inheritance

> In multiple inheritance, a class inherits from multiple interfaces. Note that C# does not support deriving multiple base classes. Use interfaces for multiple inheritance.

![The San Juan Mountains are beautiful!](https://www.tutorialsteacher.com/Content/images/csharp/inheritance6.png "San Juan Mountains")

> Important Points:

* In C#, three types can participate in inheritance: Class, Struct, and Interface.
* A class can inherit a single class only. It cannot inherit from multiple classes.
* A class cannot inherit from a struct.
* A class can inherit (implement) one or more interfaces.
* A Struct can inherit from one or more interfaces. However, it cannot inherit from another struct or class.
* An interface can inherit from one or more interfaces but cannot inherit from a class or a struct.
* Constructors or destructors cannot be inherited.


> # Polymorphism :

Polymorphism is a Greek word that means multiple forms or shapes. You can use polymorphism if you want to have multiple forms of one or more methods of a class with the same name.

> Polymorphism can be achieved in two ways :-

* Compile-time Polymorphism
* Run-time Polymorphism

### Compile-time Polymorphism : -
Compile-time polymorphism is also known as method overloading.

Method Overloading :- 
> more than one method with the same name but with different signatures. This is called method overloading.Method overloading is also known as early binding or static binding because which method to call is decided at compile time, early than the runtime.

## Rules for Method Overloading:-
* Method names should be the same but method signatures must be different. Either the number of parameters, type of parameters, or order of parameters must be different.
* The return type of the methods does not play any role in the method overloading.
* Optional Parameters take precedence over implicit type conversion when deciding which method definition to bind.

> ## Example: Method Overloading Method Overloading

class ConsolePrinter

{

    public void Print(string str){ 
        Console.WriteLine(str);
    }

    public void Print(string str1, string str2){ 
        Console.WriteLine($"{str1}, {str2}");
    }

    public void Print(string str1, string str2, string str3){ 
        Console.WriteLine($"{str1}, {str2}, {str3}");
    }
}


class ConsolePrinter

{

     public void Print(string str){ 
        Console.WriteLine(str);
    }

    public void Print(string str1, string str2){ 
        Console.WriteLine($"{str1}, {str2}");
    }

    public void Print(string str1, string str2, string str3){ 
        Console.WriteLine($"{str1}, {str2}, {str3}");
    }
	
    public void Print(int a){ 
        Console.WriteLine($"Integer {a}");
    }
	
	 public void Print(int a, string str){ 
        Console.WriteLine($"{a}, {str}");
    }

    public void Print(string str, int a){ 
        Console.WriteLine($"{a}, {str}");
    }
}


public static void Main()

{

	ConsolePrinter cp = new ConsolePrinter();
	cp.Print("Hello World!");
	cp.Print(1, "John");
}

> # Runtime Polymorphism: Method Overriding

Run-time polymorphism is also known as inheritance-based polymorphism or method overriding.

Inheritance allows you to inherit a base class into a derived class and all the public members of the base class automatically become members of the derived class. However, you can redefine the base class's member in the derived class to provide a different implementation than the base class. This is called method overriding that also known as runtime polymorphism.

> # Example: Method Overriding

class Person

{

    public virtual void Greet()
    {
        Console.WriteLine("Hi! I am a person.");
    }
}

class Employee : Person

{

    public override void Greet()
    {
        Console.WriteLine("Hello! I am an employee.");
    }
}

> Runtime Polymorphism

class Program

{

    public static void Display(Person p){ 
        p.Greet();
    }

    public static void Main()
    {
        Person p1 = new Person();
        Display(p1);
            
        Person p2 = new Employee();
        Display(p2);
            
        Employee emp = new Employee();
        Display(emp);
    }
}


Person p1 = new Person();

p1.Greet();

Person p2 = new Employee();

p2.Greet();

Employee emp = new Employee();

emp.Greet();




> Output:
* I am a human!
* I am a Manager!
* I am a Manager!


> # Rules for Overriding:

* A method, property, indexer, or event can be overridden in the derived class.
* Static methods cannot be overridden.
* Must use virtual keyword in the base class methods to  indicate that the methods can be overridden.
* Must use the override keyword in the derived class to override the base class method.

