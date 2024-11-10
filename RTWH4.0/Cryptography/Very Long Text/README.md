# A Very Long Text

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RTWH4.0/Steganography/Cat%20Sound/longte1.png" alt="Challenge Image">
</p>


The file contains a very long base64-encoded message.

## Solution
### Step 1: Understanding the Encoding
- The description hinted that the text had been encoded 26 times. Given that the text was in base64, that means I need to decode it repeatedly to reveal the original message.

### Step 2: Using CyberChef
- I uploaded the `file.txt` file to **CyberChef**.
- I used the "From Base64" operation and repeated it **26 times** to fully decode the message.

### Step 3: Obtaining the Flag
- After decoding the base64 text 26 times, the final output revealed the flag.

## Flag
`UCC{F1R5T_ST3P_G00D_J03}`  
