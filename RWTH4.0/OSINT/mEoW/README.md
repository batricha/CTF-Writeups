# mEoW

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RWTH4.0/OSINT/mEoW/meow1.png" alt="Challenge Image">
</p>


The challenge hints at a popular tourist attraction featuring a cat statue.


## Solution
### Step 1: Identifying the Location
- From the description, I recognized the cat statue as the famous **Cat Statue in Kuching, Sarawak**. This statue is a well-known landmark and tourist attraction in the area.

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RWTH4.0/OSINT/mEoW/meow2.png" alt="Hint Image">
</p>

### Step 2: Checking Recent Reviews
- I then checked the latest reviews for the Cat Statue's location. In one of the reviews, I found a hint mentioning **GitHub** and a base64-encoded string.

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RWTH4.0/OSINT/mEoW/meow3.png" alt="Hint Image">
</p>

### Step 3: Decoding the Base64 String
- I decoded the base64 string, which revealed a GitHub link.

### Step 4: Exploring the GitHub Repository
- Following the link to GitHub, I visited the profile and checked the repositories. Inside one of the repositories, I found a file labeled **flag.txt**.
- Opening the file revealed the hidden flag.

## Flag
`UCC{051NT_CH411_FUN}`  
