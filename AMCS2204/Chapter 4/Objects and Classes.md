# Procedural Paradigm vs Object-Oriented Paradigm

| Procedural Paradigm                                                                                 | Object-Oriented Paradigm                                                                      |
| --------------------------------------------------------------------------------------------------- | --------------------------------------------------------------------------------------------- |
| Data & Methods are loosely coupled                                                                  | Couples data and methods together into objects                                                |
| Software design focuses on designing methods                                                        | Software design focuses on objects and operations on objects                                  |
| As data and operations on the data are separate, this methodology requires sending data to methods. | Places data and the operations pertaining to the data within a single entity called an object |
# OO Programming Concepts (1)
- Object-Oriented Programming (OOP) involve programming using objects.
- An object represents an entity in the real world that can be distinctively identified, e.g a student, a desk, a circle, a button, a loan.
- An object is an instance of a class.
- An object has a unique identity, state and behaviors.
	- The state of an object consists of a set of data fields (also known as properties) with their current values.
	- The behavior of an object is defined by a set of methods.
# Objects
![[Pasted image 20260225121547.png]]
- An object has both a state and a behavior.
	- The state defines the object.
	- The behavior defines what the object does
## Example
```Java
public class Circle {
	double radius;

	double getArea(){
		return Math.PI * radius * radius;
	}
}

public class TestCircle {
	public static void main(String[] args){
		Circle c = new Circle();
		
		c.radius = 10;
	}
}
```
# Classes (1)
- Classes are constructs that define objects of the same type.
- A class uses
	- Variables to define data fields and
	- methods to define behaviors
- Additionally, a class provides a special type of methods known as constructors, which are invoked to construct objects from the class.
# Classes (2)
```Java
class Circle {
	/** The radius of this circle **/
	double radius = 1.0;
	/** Construct a circle object with default values **/
	Circle(){
	}
	//** Construct a circle object **/
	Circle (double newRadius){
		radius = newRadius;
	}
	/** Return the area of this circle **/
	double getArea() { // This is a method. You can have methods in your class.
		return radius * radius * 3.14159;
	}
}
```
# Declaring Object Reference Variables
- To reference an object, assign the object to a reference variable.
- To declare a reference variable, use the syntax:
  `ClassName objectRefVar;`
Example:
```Java
Circle myCircle;
	myCircle = new Circle(5.0);
```
![[Pasted image 20260225124147.png]]
# Declaring / Creating Objects in a Single Step
`ClassName objectRefVar = new ClassName();`
- Example:
  ![[Pasted image 20260225124324.png]]
  ![[Pasted image 20260225124344.png]]
# Accessing Objects
- Referencing the object's data:
  `objectRefVar.data`
Example : 
  ```Java
  Circle myCircle = new Circle (10);
  System.out.println(myCircle.radius);
  ```
  - Invoking the Object's method: 
    `objectRefVar.methodName (arguments)`
Example: 
`System.out.println(myCircle.getArea())`

# Classes
- A class is a template that defines the form of an object.
- A class consists of 2 parts:
	- Data Members
		- Data or properties of a class
		- The nouns of the class.
		- Represents the state of its objects.
	- Method Members
		- Functions or actions of a class
		- The verbs of the class
		- The code that will operate on the data of the class
		- Implementation of its object's behaviors
![[Pasted image 20260225130259.png]]
# Object Vs Class

| Object                                                                                                        | Class                                                                   |
| ------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| An object is an instance of exactly one class.                                                                | A class is a logical abstraction                                        |
| Only when we create an object, then we have an actual physical representation of that class exists in memory. | Defines what data to store and what actions we can operate on the data. |
NOTE: One object can have only one class while one class can have multiple objects.
![[Pasted image 20260225131141.png]]
# Defining a Class
```Java
public class <class name>{
	//Declare instance variables
	type var1;
	type var2;
	
	//Declare methods
	Method 1
	Method 2
}
```
