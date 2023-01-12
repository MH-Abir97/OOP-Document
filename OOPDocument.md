
## Object-oriented programming is a real-world programing.Object-oriented programming is a way of developing software applications using real-world terminologies to create entities that interact with one another using objects. 


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