# Challenge 5

```python
def evaluate_strength(passwd):
    
    score = 0
    
    l = len(passwd)
    uc = 0
    lc = 0
    sc = 0
    nc = 0
    
    for i in passwd:
        
        if i.isalnum():
            if i.isupper():
                uc += 1
            elif i.islower():
                lc += 1
            else:
                nc += 1
        elif i == " ":
            print("Spaces are not Allowed")
            return
        else:
            sc += 1
    
    if (l / 8) * 20 > 20:
        score += 20
    else:
        score += (l/8) * 20
    
    for k in [uc,lc,sc,nc]:
        if k == 1:
            score += 10
        elif k >= 2:
            score += 20
    
    return score

password = input("Enter your password: ")
print("Password strength: ", evaluate_strength(password))
```