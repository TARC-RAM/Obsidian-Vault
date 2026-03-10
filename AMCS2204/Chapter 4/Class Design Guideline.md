# Cohesion
- A class should describe a single entity
- All the class operations should logically fit together to support a coherent purpose.
# Consistency
- Follow standard Java programming style and naming conventions.
	- Choose informative names for classes, data fields and methods.
	- Always place the data declaration before the constructor, and place constructors before methods.
	- Always provide a constructor and initialize variables to avoid programming errors.
- Provide a public no-arg constructor
# Encapsulation
- Class should use the private modifier to hide its data from direct access by clientes
	- Use get methods and set methods to provide access to private data.
- A class should also hide methods not intended for client use.
# Instance vs Static
| Concept                        | Explanation                                                                                                         | Example / Rule                                                          |
| ------------------------------ | ------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------- |
| **Instance Variable / Method** | Used when the data or behavior belongs to a specific object of a class. Each object has its own copy.               | Example: Each `Circle` object has its own `radius`.                     |
| **Static Variable**            | Used when the data is shared among all objects of a class. Only one copy exists for the entire class.               | Example: `numberOfObjects` counting all created `Circle` objects.       |
| **Static Getter / Setter**     | Methods used to access or modify static variables should also be declared `static`.                                 | `public static int getNumberOfObjects()`                                |
| **Referencing Static Members** | Static variables and methods should be accessed using the **class name**, not an object reference.                  | `Circle.getNumberOfObjects()` instead of `circle1.getNumberOfObjects()` |
| **Static Initialization Rule** | Constructors should **not** receive parameters to initialize static variables. Use a separate `set` method instead. | `Circle.setNumberOfObjects(10)`                                         |
# Collection of Objects
- One way to store a collection of objects is to declare an array of objects.
# Association
- A general relationship that describes an activity between two classes, where one class is related to another class in some way
- This is a very basic form of relationship and doesn't imply any specific dependency or behavior.
# Terminology
![[Pasted image 20260308150930.png]]
![[Pasted image 20260308150938.png]]

# Aggregation
- An object can contain another object.
- Aggregation models **has-a** relationship
	- Represents and ownership relationship between two objects.
- An object may be owned by several other aggregating objects.
# Object Composition
- If an object is exclusively owned by an aggregating object, the relationship between them is referred to as composition.
- Composition is actually a special case of the aggregation relationship
- If a relationship is composition, the aggregated object cannot exist on its own
# Aggregation vs Composition 
- Aggregation: typically involves one-to-many relationship
- Composition: typically involves one-to-one relationship
- Example:
	- Name & Student (Composition): A name can only be part of student
	- Address & Student (Aggregation): An address can belongs to many students.
	  ![[Pasted image 20260308154250.png]]
- Example:
	- Name & Student (Composition): When Student entity is destroyed, Name entity cannot exists on its own.
	- Address & Student (Aggregation): When Student entity is destroyed, Address entity can still exists on its own.
	  ![[Pasted image 20260308154451.png]]
# Aggregation and Composition Example
![[2026-03-08-154453_hyprshot.png]]
# Multiplicity
![[Pasted image 20260308154613.png]]
# Implementing Aggregation
- An aggregation relationship is usually represented as a data field in the aggregating class.
  ![[Pasted image 20260308154746.png]]
- See Name.java, Address.java, Student.java, TestStudent.java