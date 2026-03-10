# The Date Class
- Java provides a system-independent encapsulation of date and time in the java.util.Date class.
- You can use the **Date** class to create an instance for the current date and time and use its **toString** method to return the date and time as a string.
# The Random Class
- The **Math.random()** method returns a random double value between 0.0 and 1.0 (excluding 1.0).
- The **java.util.Random class** provides more useful random number generators
## Example
- If two Random objects have the same seed, they will generate identical sequences of numbers. For example, the following code creates two Random objects with the same seed 3.
  
  # Instance Variables and Methods
- Instance variables belong to a specific instance.
- Instance methods are invoked by an instance of the class.
```Java
  public class Circle {

    private double radius;          // The radius of the circle
    private static int numberOfObjects = 0;   // Number of objects created

    public Circle() {
        radius = 1.0;
        numberOfObjects++;
    }

    public Circle(double newRadius) {
        radius = newRadius;
        numberOfObjects++;
    }

    public static int getNumberOfObjects() {
        return numberOfObjects;
    }

    public double getArea() {
        return radius * radius * Math.PI;
    }

}
```
# Static Variables, Constants and Methods
- Are shared by all the instances of the class.
- May be accessed using the object name or the class name
- The value for a static variable is stored in a common memory location.
- All objects will be affected if one of them changes the value of the static
  ![[Pasted image 20260308140206.png]]
- Static methods are not tied to a specific object.
- Static constants are final variables shared by all the instances of the class.
- To declare static variables, constants and methods, use the static modifier.
  ![[Pasted image 20260308140358.png]]
- radius is an instance variable.
- numberOfObjects is a static variable.
- getNumberOfObjects() is a static method.
- GetArea() is an instance method.
