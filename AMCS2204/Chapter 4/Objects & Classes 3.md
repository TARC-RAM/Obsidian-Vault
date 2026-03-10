# Encapsulation
- Encapsulation is a programming mechanism that binds together code and the data it manipulates.
	- This keeps both data and code safe from external interference and misuse.
- In an OO language, code and data can be bound together in such a way that a self-contained black box is created.
	- Within the box are all necessary data and code.
	- When code and data are linked together in this fashion, an object is created.
- **Thus, an object is the device that supports encapsulation**
- Within an object, code, data, or both may be private to that object or public.
	- Private code or data is known to and accessible by only another part of the same object, i.e they cannot be accessed outside the object. 
	- Public code or data may be accessed by other parts of the program.
	- Typically, the public methods of an object are used to provide a controlled interface to the private elements of the object.
	  ![[Pasted image 20260308155857.png]]
- In an OO language, the basic unit of encapsulation is the class.
	- A class defines the form of an object. It specifies both the data and code that will operate on the data.
- In its support for encapsulation, the class provides 2 major benefits:
	- It links data with the code that manipulates it.
	- It provides means by which access to members can be controlled.
	  ![[Pasted image 20260308160120.png]]
# Controlling Access to Class Members
- Restricting access to class's members is a fundamental part of OOP because it helps prevent the misuse of an object.
- By allowing access to private data only through a well-defined set of methods,
	- You can prevent improper values from being assigned to that data (e.g by performing a range check).
	- It is not possible for code outside the class to set the value of a private member directly.
	- You can also control precisely how and when the data within an object is used
# Class Abstraction
- OOP provides many levels of abstraction
	- Method abstraction
	- Class abstraction
- Class abstraction means to separate class implementation from the use of the class.
	- The creator of the class provides a description of the class and lets the user know how the class can be used.
	- The user of the class does not need to know how the class is implemented.
- The details of implementation are encapsulated and hidden from the user - this is known as class encapsulation.
  ![[Pasted image 20260308163821.png]]
- The collection of methods and fields that are accessible from outside the class, together with the description of how these members are expected to behave, serves as the class contract.
- E.g you can create a Circle object and find the area of the circle without knowing how the area is computed.
  ![[Pasted image 20260308180113.png]]
# Class User and Class Writer
As a programmer, you will play the role of both class user and class writer.