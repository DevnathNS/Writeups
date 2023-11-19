# Challenge 2

```python
def possible(lst,k):
    l = len(lst)
    for e, i in enumerate(lst):
        if i == 0:
            indexf = 0
            indexb = 0
            for j in range(e + 1, l):
                if lst[j] == 0:
                    indexf = j
                    break
            for m in range(e - 1, -1, -1):
                if lst[m] == 1:
                    indexb = m
                    break
            fd = abs(indexf - e)
            bd = abs(e - indexb)
            if fd <= k-1 or bd <= k-1:
                continue
            else:
                return False
        else:
            continue
    return True

k=int(input("k = "))
lst = eval(input())
if possible(lst,k):
    print("YES")
    print((len(lst)-k) // lst.count(1))
else:
    print(-1)
```