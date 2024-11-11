# keripto

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RTWH4.0/Steganography/WOWERRZZZZ/wowerrzzzz1.png" alt="Challenge Image">
</p>

The challenge provided an encryption script, `enc.py`, which when executed outputs an IV and a ciphertext. Our goal was to decrypt the ciphertext and retrieve the flag.



## Solution
### Step 1: Running `encrypt.py`
After examining and running `encrypt.py`, the following output was generated:

- **IV (hex)**: `880e041c917f59140ab085dd4a5caf41`
- **Ciphertext (hex)**: `c64a7b47f47912427e4aecd5da1bd230`

### Step 2: Analyzing `encrypt.py`
From reviewing the `encrypt.py` code, I noted that:
- The script uses **AES encryption** in **CBC mode**.
- It uses a hardcoded key, so the same key can be used for decryption.
- The IV and ciphertext are both required for decrypting the message.

### Step 3: Writing `decrypt.py`
To decrypt the ciphertext, I created `decrypt.py` with the same AES key, IV, and ciphertext values. Here’s the code I used:

```python
from Crypto.Cipher import AES
from Crypto.Util.Padding import unpad
import binascii

# Provided data
ciphertext_hex = "c64a7b47f47912427e4aecd5da1bd230"
iv_hex = "880e041c917f59140ab085dd4a5caf41"
key = b'Sixteen byte key'  # same key as in encrypt.py

# Convert hex values to bytes
ciphertext = bytes.fromhex(ciphertext_hex)
iv = bytes.fromhex(iv_hex)

# Initialize cipher for decryption
cipher = AES.new(key, AES.MODE_CBC, iv)
decrypted = unpad(cipher.decrypt(ciphertext), AES.block_size)

# Print the decrypted message
print("Decrypted message:", decrypted.decode()) ```

### Step 4: Running `decrypt.py`
- After running decrypt.py, the decrypted message revealed the flag.

## Flag
`UCC{they have crypto chal for beginner?!?!}`  
