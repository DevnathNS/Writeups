# Challenge 6

```python
def arrange(array, count):
    # array = [a, c, b]
    sa = sorted(array) # [a, b, c]
    operations = 0
    
    if array == sa:
        print("YES")
        return
    
    for i in range(0,len(array)): # 0, 1
        if array[i] != sa [i]: # a == a, c != b
            k = sa.index(array[i]) # k = 2
            temp = array[k] # temp = b
            array[k] = array [i] # array = [a, c, c]
            array[i] = temp # array = [a, b, c]

            operations += 1 # operations = 1

        if array == sa: # iteration 2: [a, b, c] = [a, b, c]
            break
        
    if operations <= count:
        print("YES")
    else:
        print("NO")

                    

arr = list(input())
count = int(input())
print (arrange(arr,count))
```