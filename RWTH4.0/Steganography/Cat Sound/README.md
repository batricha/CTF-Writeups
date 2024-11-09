# Cat Sound

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RWTH4.0/Steganography/WOWERRZZZZ/wowerrzzzz1.png" alt="Challenge Image">
</p>


The challenge provides a `.wav` audio file and a hint in base64. 
Full Hint: aHR0cHM6Ly9naXRodWIuY29tL0pwaW5zb2Z0L0RlZXBTb3VuZAo=

## Solution
### Step 1: Decoding the Hint
- The hint provided in base64 was decoded using a base64 decoder.
- The decoded hint contained a link to a GitHub repository.

### Step 2: Downloading and Using DeepSound
- The GitHub repository instructed me to download **DeepSound**, a tool used for steganography in audio files.
- After downloading and opening **DeepSound**, I loaded the `audio.wav` file into the program.

### Step 3: Guessing the Password
- DeepSound asked for a password to unlock the hidden content in the audio file.
- I guessed the password as `meow`, and it worked.

### Step 4: Extracting the Flag
- Once the password was entered, DeepSound granted access to a hidden file called **meow.txt**.
- Inside **meow.txt**, I found the flag.

## Flag
`UCC{F0R351C_Y0UR_FR313N8}`  
