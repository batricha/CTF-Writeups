# WOWERRZZZZ

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RWTH4.0/Steganography/WOWERRZZZZ/wowerrzzzz1.png" alt="Challenge Image">
</p>


The challenge provides a `.jpg` file of a cat

<p align= "center">
 <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RWTH4.0/Steganography/WOWERRZZZZ/WOW.jpg" alt="WOW Image">
</p> 

Attachment: WOW.jpg

## Solution
### Step 1: Initial Observations
- After examining `wow.jpg`, I confirmed it was a valid JPG image file. 
- The cat image appeared clear in the upper half and blurry in the lower half. This might be a hint that hidden information is embedded within the file’s data, not necessarily visible in the image.

### Step 2: Extracting Text with `strings`
- **Command Used**: `strings WOW.jpg | grep UCC`
- **Reasoning**: In steganography challenges, data is often embedded within an image file's metadata or hidden as readable text within the binary file. Since “UCC” was provided as the beginning of the flag, I used `strings` to extract all readable text and filtered results with `grep UCC`.

### Step 3: Result
- The command output included the hidden flag, confirming that the solution was embedded as text within the image file itself.

## Flag
`UCC{0Y3N_8R0K3N_F0R3V3R}`  
