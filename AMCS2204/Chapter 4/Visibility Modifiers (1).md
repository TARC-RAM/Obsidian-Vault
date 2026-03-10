643- Restricting access to a class members is a fundamental part of OOP because it helps prevent misuse of an object.
- Member access control is achieved through the use of 4 visibility modifiers:
	- Default
		- By default, the class, variable or method can be accessed by any class in the same package (folder)
	- Public
		- The class, data or method is visible to any class in any package.
	- Private
		- The data or methods can be accessed only by the declaring class.
	- Protected
# Why Data Fields Should Be private?
- Prevent data from being tampered
- Makes the class easier to maintain and less vulnerable to bugs.
- A client can retrieve and modify a data field by providing accessor and mutator methods.
# Accessor/Mutator Methods
- Accessor methods
	- Methods used to read private properties.
		- Getter or get methods
	- Has the following method signature:
		- public returnType getPropertyName()
- Mutator methods
	- Methods used to modify private properties.
		- Setter or set methods.
	- Has the following method signature:
		- public void setPropertyName(datatype propertyValue)