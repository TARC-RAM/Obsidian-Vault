# Structured Design
- Dividing a problem into smaller subproblems
- Has multiple names such as:
	- Top-Down design
	- Stepwise refinement
	- Modular programming

Implementing a structured design require us to:
1) Divide the problem into smaller problems.
2) Analyses each subproblem and obtain a solution to solve the sub problem
3) The solutions of all the subproblems are then combined to solve the overall problem
# Object-Oriented Design
In Object-Oriented Design (OOD), the steps in the process include:
1) Identify the objects for the problem.
2) Specify for each object the relevant data and possible operations to be performed on that data.
3) Determine how the various objects interact with one another.
## Object
- An object represents an entity in the real world that can be distinctly identified.
- An object consist of its unique state (data), and behavior (methods).
- For example, a student, a desk, a circle, a button and even a loan can all be viewed as objects.
### Object Data (Attribute / Fields)
- State of an object (also known as attributes) is represented by data fields with their current values.
- Example:
	- Customer Name (custName)
	- Number of rooms (NoOfRooms)
### Object Operations (Methods / Action)
- Object Operations (Also known as method) is invoked on an object to perform a specific action.
- Example:
	- Check the availability of the rooms
	- Change the status of the room once occupied
	- Check the number of room available
# Basic Principles of OO Design
- **[[Encapsulation]]** - all about wrapping variables and methods in one single unit with the sole purpose of data hiding from external classes. 
- Inheritance - The ability to create new classes from existing classes.
	- Inheritance enables you to define a general class (i.e a superclass) and later extend it to more specialized classes (i.e subclasses).
- Polymorphism - The ability to use the same expression to denote different operations.
## Class
- A class is a template or a blueprint that defines what an object's data fields and methods will be.
- Classes are used to create and manage new objects
- In OOP languages, [[Encapsulation]] is accomplished via the use of the data types called classes.
- In OOD, you decide which classes you need and what are their relevant data fields (variables) and methods (functions for the operations)
## Object
- An object is an instance of a class.
- You can create as many instance of a class as you wish.
- [[Instantiation]] is referred to creating an instance for the object.
- The term object and instance is interchangeable (means they're the same)
- Objects interact with each other via method calls