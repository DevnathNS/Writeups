# Challenge 4

```python
def strip_zeroes(lst):
    l = len(lst)
    
    index = 0

    for i in range(l):
        if lst[i] != 0:
            index = i
            break
        
    new_list = lst[index:l]
    return new_list

def min_operations(chambers):
    chambers = strip_zeroes(chambers)
    zc = chambers.count(0)
    min_steps = zc + sum(chambers) - chambers[-1]
    
    return min_steps

chambers = [int(num) for num in input().split()]
print(min_operations(chambers))
```