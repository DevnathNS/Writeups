# “Encimage”

First, I opened the corrupted file using HxD to view the hex.

![Untitled](%E2%80%9CEncimage%E2%80%9D%20daad72093c8c4a2784fe8e7a29707488/Untitled.png)

Since it was encrypted, the next order of business was to find the key. Since the first eight bytes are the same in every png file, I used the magic numbers as my “plaintext” and the first eight bytes of the encrypted png file as the “ciphertext”. I used the following code, which yielded the key, “pngforen”. 

 

```python
mn=['\x89','\x50','\x4e','\x47','\x0D','\x0A','\x1A','\x0A']
enc = ['\xF9', '\x3E', '\x29', '\x21','\x62', '\x78', '\x7F', '\x64']

key=""

for i in range(0,8):
    key += chr(ord(mn[i])^ord(enc[i]))

print(key)
```

`pngforen`

Now that I had the key, I had to decrypt the entire hex. For the same, I used pwn.

![Untitled](%E2%80%9CEncimage%E2%80%9D%20daad72093c8c4a2784fe8e7a29707488/Untitled%201.png)

Next, I opened the newly saved “decrypted.png” file and saw that it was a QR code.

![Untitled](%E2%80%9CEncimage%E2%80%9D%20daad72093c8c4a2784fe8e7a29707488/Untitled%202.png)

Now, what I had to do was extract the data from the QR code. For that, I used `zbarimg`. It yielded the flag.

![Untitled](%E2%80%9CEncimage%E2%80%9D%20daad72093c8c4a2784fe8e7a29707488/Untitled%203.png)