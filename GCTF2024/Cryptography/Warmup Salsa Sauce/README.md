# Warmup Salsa Sauce

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/GCTF2024/Cryptography/Warmup%20Salsa%20Sauce/warmup1.png" alt="Challenge Image">
</p>


The challenge provided two files: wss.py and out.txt. The objective was to decrypt the encrypted message using the information provided in these files.

## Analysis

By examining the source code in wss.py, I determined that the encryption algorithm used is **Salsa20**. This was also hinted at by the challenge title, "Warmup Salsa Sauce." 

In Salsa20, encryption and decryption involve an XOR operation:
- **Ciphertext** = Plaintext XOR Key
- **Key** = Plaintext XOR Ciphertext

Since we have access to both the plaintext (from wss.py) and the ciphertext (from out.txt), we can derive the **key** by XOR-ing the plaintext with the ciphertext. Once we have the key, we can use it to decrypt the flag.

## Solution

### Step 1: Examine the Files
- **wss.py**: Contains the source code that performs the encryption using Salsa20.
- **out.txt**: Contains the encrypted text (ciphertext).

### Step 2: Create a Script to Derive the Key and Decrypt the Flag
- Using the XOR logic, I created the following script, enc.py, to derive the key and decrypt the message.

```python

from binascii import unhexlify

# Encrypted data from out.txt
encrypted_flag = unhexlify("fa1c26b66ad926ab75cd51524f05ec08f7f3160c74bec57f8aec3f7cace6fbb7370923e8c548673f657dada99540101d7f4dc0b6627f147fc47627a244c88b2eac3340")
encrypted_text = unhexlify("falc26b66ad926ab45cb05575b0ab99fcdf1060d72bfba6f90aa076cbcf2f3a311a13fc800638382570bcbee142001290f1d41d3761e315b91730663c2cdbe7a25482ce0c69745028635ef5dae54282f1622448fec5f6b0e7d8ff85")
plaintext = b"We covered the drugs with our favourite salsa sauce. The stupid cops will not find it."

# Since Salsa20 uses the first 8 bytes as the nonce, we want to skip that
nonce_len = 8
ciphertext_without_nonce = encrypted_text[nonce_len:]

# After nonce, XOR the encrypted text with the plaintext to get the keystream.
keystream = bytes(a ^ b for a, b in zip(ciphertext_without_nonce, plaintext))

# Skipping the first 8 bytes as the nonce in encrypted flag as well
cipher_flag_without_nonce = encrypted_flag[nonce_len:]

# Now, XOR the keystream with the encrypted flag to recover the flag
flag = bytes(a ^ b for a, b in zip(cipher_flag_without_nonce, keystream))

# Printing out the decrypted flag
print(flag.decode())
```

### Step 3: Run the Script
- Running the script with the derived key will output the decrypted flag.


## Flag
`gctf{y0u_f0und_th3_c0cain3_a7f9f6bdeabd34dde0fa3037284864eb}`
