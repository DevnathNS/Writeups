# Basic mod 1

```python
x = [350, 63, 353, 198, 114, 369, 346, 184, 202, 322, 94, 235, 114, 110, 185, 188, 225, 212, 366, 374, 261, 213]
y = []
for i in range(len(x)):
    y.append(x[i] % 37)
flag = "picoCTF{"
for j in y:
    if 0 <= j <= 25:
        flag += chr(65 + j)
    elif 26 <= j <= 35:
        flag += str(j - 26)
    elif j == 36:
        flag += "_"
flag += "}"
print(flag)
```