# Challenge 1

```python
def check(array):
    a = min(array)
    
    if array.count(a) > 1:
        if a != 0:
            array.remove(a)
            array.append(0)
            return True
        
    return False

def equalize(array):
    count = 0
    
    while sum(array) > 0:
        
        length = len(array)
        
        if max(array) == min(array):
            array.remove(max(array))
            array.append(0)
            
        else:
            a = max(array)
            b = min(array)
            array.remove(a)
            a = b
            array.append(a)
        
        if check(array):
            count += 2
            
        else:
            count += 1

    return count

array = [int(num) for num in input().split()]
print(equalize(array))
```