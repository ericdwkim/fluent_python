# Reference Notes 

## Concepts & Takeaways

- Leverage built-in dunder methods instead of re-creating the wheel as new methods

## Terminology
- infix operators -> create new objs and not touching/modifying the operands

Example: This addition function simply *reads* the operands `self` and `other` , but does not modify them and ultimately returns the new object.

```
class Vector:
                ...
           
    def __add__(self, other):
        x = self.x + other.x
        y = self.y + other.y
        return Vector(x, y)
```


- 