# Cryptopals

### **Challenge 1**

```python
from base64 import b16decode, b64encode

string = "49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d"
print(b16decode(string.upper()))

b_64 = b64encode (b16decode(string.upper()))
print(b_64)
```

### Challenge 2

```python
def fixed_xor(a, b):
              
    int1 = int(a, 16)
    int2 = int(b, 16)

    # Perform XOR operation
    result = int1 ^ int2

    # Convert the result back to a hexadecimal string
    result_hex = hex(result)

    return result_hex

a = "1c0111001f010100061a024b53535009181c"
b = "686974207468652062756c6c277320657965"

print(fixed_xor(a,b))
```