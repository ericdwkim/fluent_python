# Reference Notes 

## Concepts & Takeaways

- Leverage built-in dunder methods instead of re-creating the wheel as new methods
- Abstract Base Classes (ABCs) --> enforces its subclasses to implement specific methods; ensures consistency and reliability of the interface
- Polymorphism --> provides flexibility and extensibility to parent class methods, thus ensuring interface uniformity

## Terminology
- **infix operators** -> create new objs and not touching/modifying the operands

Example: This addition function simply *reads* the operands `self` and `other` , but does not modify them and ultimately returns the new object.

```
class Vector:
                ...
           
    def __add__(self, other):
        x = self.x + other.x
        y = self.y + other.y
        return Vector(x, y)
```

- **Container sequences** -> versatile; can be more memory intensive as it must hold both a ref and the obj in memory, but flexible in that it can hold memory of any dtype
- **Flat sequences** -> homogenous data (only single dtype allowed); less memory intensive; stores the value of each item 

## Special methods

`__repr__` --> provides a helpful, string representation of an object for inspection

For example, the output `Vector(4, 5)` is descriptive of how the Vector class is defined. This output can also now be used as an input too. Without this custom method, we would see `<Vector object at 0x...>` which isn't helpful or descriptive. 

```
    def __repr__(self):
        return f'Vector({self.x!r}, {self.y!r})'
    
    v1 = Vector(2, 4)
    v2 = Vector(2, 1)
    v3 = v1 + v2
    
>> Vector(4, 5)
```

## Syntax 

`!r` in the `__repr__` allows `Vector(2, 4)` and `Vector('2', '4')` to be both valid instead of expecting the x, y values to be ints, so the returned string would output the more accurate dtypes of the args

## Data Structures

- Dynamic arrays = lists (mutable) 
- Fixed-size arrays = tuples (immutable)