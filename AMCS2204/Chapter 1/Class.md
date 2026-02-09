A class is a user-defined construct  in programming that defines the attributes and methods of objects created from it



```Python
class Person:
    species = "Human"        # class attribute

    def __init__(self, name, age):
        self.name = name     # instance attribute (string)
        self.age = age       # instance attribute (int)

    def birthday(self):
        self.age += 1


```
`def __init__` - initialize the instance attributes

## Example:
`adam = Person("Adam", 30)`
Python internally does:
1. Create a new empty `Person` object
    
2. Call `__init__` on that object with `name="Adam"` and `age=30`
    
3. Inside `__init__`, `self.name = name` and `self.age = age` run
    
Without `__init__`, you’d have to manually set every attribute **after creating the object**. That’s tedious.

## Why not just write `def info`?
1. You **can** write `info`, but it’s a normal method
    
2. Else, You would have to **call it manually** after creating the object
    
```Python
adam = Person.info("Adam", 30)  # ❌ This is wrong 
```

```Python
adam = Person()                  # Do first to create the object 
adam.info("Adam", 30)            # Do this after creating the object

```
`__init__` guarantees the object is ready to use **immediately** after creation