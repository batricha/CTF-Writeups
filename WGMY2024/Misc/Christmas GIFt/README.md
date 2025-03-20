# Christmas GIFt

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Misc/Christmas%20GIFt/gift4.png" alt="Challenge Image">
</p>


The prompt provided a `.gif` file of a present box being opened, but nothing came out of it.

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Misc/Christmas%20GIFt/gift3.png" alt="Challenge Image" width="490" height="420">
</p>

## Analysis & Solution

### Step 1: Analyzing the File
- I began by examining the file format using various tools like `file`, `exiftool`, and `binwalk` to check for hidden data or embedded files.
- None of these tools revealed anything unusual about the `.gif` file.

### Step 2: Visual Inspection in GIMP
- I opened the `.gif` file in GIMP to examine the individual frames.
- Upon scrolling through the frames, I discovered one frame that contained the flag.

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Misc/Christmas%20GIFt/gift2.png" alt="Flag Image" width="490" height="420">
</p>

### Step 3: Submitting the Flag
- I noted down the text from the frame and submitted it as the flag.

### 🔙 [Back to WGMY2024 Challenge Menu](https://github.com/batricha/CTF-Writeups/tree/main/WGMY2024)
