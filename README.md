# Reference Notes 

## Concepts & Takeaways

- Leverage built-in dunder methods instead of re-creating the wheel as new methods

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

## Special methods

`__repr__` --> provides a helpful, string representation of an object for inspection

For example, the output `Vector(4, 5)` is descriptive of how the Vector class is defined.

```
    def __repr__(self):
        return f'Vector({self.x!r}, {self.y!r})'
    
    v1 = Vector(2, 4)
    v2 = Vector(2, 1)
    v3 = v1 + v2
    
>> Vector(4, 5)
```

