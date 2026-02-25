Array is a data structure that represents a collection of the same types of data
## Declaring Array Variables
### There are two ways to declare an Array
- datatype[] arrayRefVar;
	- Example: double[] myList //Preferred style
- datatype arrayRefVar[];
	- Example: double myList[]; //Not Preferred
## Creating Arrays
The declaration of an array does not allocate any space in memory for the array.
The array variable only creates a storage location for the *Reference to the array*
Array elements cannot be assigned to an array unless the array has already been created.
If the array variable does not refer to an array (i.e the array has not been created), the value of the array variable is null.
## Eg: double[] myList;
myList holds the value of null since there is no reference to the array variable.

To create an array, use the **new** operator.
- Syntax:
  ```Java
  arrayRefVar = new datatype[arraySize];
  ```
- Example
  ```Java
  double[] myList; //Currently Null
  
  myList = new double [10]; //size of the array is now 10 (0 - 9)
  ```
![[Pasted image 20260211121726.png]]
You can also combine Array declaration and creation.
```Java
datatype[] arrayRefVar = new datatype[arraySize];

double myList[] = new double[10];
```
![[Pasted image 20260211122205.png]]
## The Length of an Array
Once an array is created, its size is fixed and therefore cannot be changed.
In java, the array's size may be obtained using arrayRefVar.lenth
```Java
double myList[] = new double[10];
int length = myList.length;
```
## Default Values
When an array is created, its elements are assigned the default value of
- 0 for numeric primitive data types.
- '\u0000' for char typed array elements
- false for boolean typed array elements
  ![[Pasted image 20260211122519.png]]
## Indexed Variables
In Java, array indexing is similar to C.
Array indices are 0-based i.e it starts from 0 to **arrayRefVar.length-1**
Each element n the array is represented using the following syntax, known as an indexed variable:
```Java
arrayRefVar[index]
```
![[Pasted image 20260211122910.png]]
## Array Initializers
Declaring, creating and initializing in one step:
```Java
double[] myList = {1.9, 2.9, 3.4, 3.5};
```
the new operator is not required.
The above shorthand notation is equivalent to the following statements;
```Java
double[] myList = new double[4];
myList[0] = 1.9;
myList[1] = 2.9;
myList[2] = 3.4;
myList[3] = 3.5;
```
![[Pasted image 20260211123148.png]]

## **CAUTION**
Using the shorthand notation, you have to declare, create and initialize the array all in one statement.
```Java
double[] myList = {1.9, 2.9, 3.4, 3.5};
```
Splitting it would cause a syntax error.
```Java
double[] myList;                //THIS IS
myList = {1.9, 2.9, 3.4, 3.5};  //VERY WRONG
```
## *foreach* Loop
The *foreach* loop enables you to traverse the complete array sequentially without using an index variable.
```Java
for(elementType value: arrayRefVar){
	//Process the value
	}
```
Example: To display all elements in the array **myList**
```Java
for (double value : myList){
	System.out.println(value);
	}
```

In java, braces are **OPTIONAL** when the loop body has **ONLY ONE** statement.
## Analyzing Array Elements 
## Copying Arrays
In java, the assignment operator may be used to copy the primitive data type variables, but not arrays.
```Java
double[] myList = {1.9, 2.9, 3.4, 3.5};
double[] newList = myList; // does not copy 
```
Assigning one array variable to another array variable *copes one **reference** to another* and makes both *variables **point** to the **same memory location***
![[Pasted image 20260211125121.png]]
### Ways to copy arrays:
1) Use a loop:
   ```Java
   int[] sourceArray = {2, 3, 1, 5, 10};
   int[] targetArray = new int[sourceArray.length];
   ```
   ![[Pasted image 20260211125258.png]]
   ``` Java
   for (int i = 0; i < sourceArray.length; i++){
   targetArray[i] = sourceArray[i];
   }
   ```
2) Use the **arraycopy** method from the **java.lang.System** class
   ```Java
   arraycopy(sourceArray, src_position, targetArray, target_position, length) 
   
   System.arraycopy(oldArray, 0, newArray, 0, oldArray.length);
   ```
   - The **arraycopy** method does not allocate memory space for the target array, i.e the target array must have already been created.
   - After copying, the target array and source array have the same content but independent memory locations.
## Exercise
```Java
int[] arrayA = {1, 2, 3, 4, 5, 6, 7, 8, 9};

int[] arrayB = new int[5];

int[] arrayC = new int[3];

int[] arrayD = new int[10];
```
a) Copy the first 5 elements of arrayA into arrayB.
```Java
System.arraycopy(arrayA, 0, arrayB, 0, 5)
```
b) Copy the last 3 elements of arrayA into arrayC.
```Java
System.arraycopy(arrayA, 6, arrayB, 0, 3)
```
c) Copy the middle 3 elements of arrayA into arrayD.
```Java
System.arraycopy(arrayA, 3, arrayB, 0, 3)
```
## Passing Arrays to Methods
```Java
//Invoke the method
int[] list = {3, 1, 2,6 ,4 ,2};
printArray(list);
             ^
             |
             |
public static void printArray(int[] array) {
for (int i = 0; i < array.length; i++) {
	System.out.print(array[i] + " ");
 }
}
```
## Anonymous Array

```Java
public static void printArray(int[] array){
    for (int i = 0; i < array.length; i++){
        System.out.print(array[i] + " ");
    }
}
```
``` Java
int[] oddNumbers = {1, 3, 5, 7, 9};
printArray(oddNumbers);
```
1. `oddNumbers` (which contains {1, 3, 5, 7, 9}) gets passed to the method
2. Inside the method, it's now called `array`
3. Loop runs: `i = 0` prints `array[0]` which is 1
4. `i = 1` prints `array[1]` which is 3
5. And so on...

**Output:** `1 3 5 7 9`
## Pass By Value
```Java
public static void main(String[] args) {
    int[] y = {10, 20, 30, 40, 50};  // Array with values
    
    System.out.println("Before: y[0] is " + y[0]);  // prints 10
    
    m(y);
    
    System.out.println("After: y[0] is " + y[0]);  // prints 5555
}

public static void m(int[] numbers) {
    numbers[0] = 5555;  // Changes the original array
}
```

**Output:**
```
Before: y[0] is 10
After: y[0] is 5555

Before: x is 1
After: x is still 1 //We did not 'return number;' at the end of the method
```
## HEAP
The JVM stores the array in an area of memory, called *heap*, which is used for dynamic memory allocation where blocks of memory are allocated and freed in a (random unpredictable order/arbitrary order).
![[Pasted image 20260211144903.png]]
![[Pasted image 20260211144939.png]]
## Returning an Array from a Method
```Java
int[] list1 = new int[]{1, 2, 3, 4, 5, 6};
int[] list2 = reverse(list1);

public static int[] reverse(int[] list) {
    int[] result = new int[list.length];
    for (int i = 0, j = result.length - 1; i < list.length; i++, j--) {
        result[j] = list[i];
    }
    return result;
}
```
- `list1` has `{1, 2, 3, 4, 5, 6}`
- Call `reverse(list1)`
- Inside method: create empty array `result` with same length (6)
- Loop with two counters:
    - `i` starts at 0, goes forward
    - `j` starts at 5 (last index), goes backward
- Copy elements: `result[j] = list[i]`
    - `result[5] = list[0]` → result[5] = 1
    - `result[4] = list[1]` → result[4] = 2
    - `result[3] = list[2]` → result[3] = 3
    - etc.
- Return the reversed array
- `list2` now has `{6, 5, 4, 3, 2, 1}`
## Variable-Length Argument Lists (Optional)