# The DCM Meta

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Misc/The%20DCM%20Meta/dcm1.png" alt="Challenge Image">
</p>


The challenge provided a `challenge.dcm` (and I realised that the hint they gave later on was sooo straightforward)


## Analysis & Solution

### Step 1: Inspecting the File
- Running the `file` command on `challenge.dcm` indicated that it was a generic data file, without identifying a specific format like DICOM or others.
- To investigate further, I opened the file in **HxD**, a hex editor.

### Step 2: Analyzing Hex Dumps
- The hex dump revealed the presence of the string WGMY (the flag format) followed by a sequence of numbers.
- After hearing that my friend tried to sort it out it gave me idea that these are the flag strings but they were out of order.

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Misc/The%20DCM%20Meta/dcm2.png" alt="Challenge Image" width="490" height="420">
</p>

### Step 3: Sorting the Strings
- Using the array provided in the description, I wrote a Python script to rearrange the strings based on the given sequence.

```python

original_rank = "f63acd3b78127c1d7d3e700b55665354"
arrangement = [25, 10, 0, 3, 17, 19, 23, 27, 4, 13, 20, 8, 24, 21, 31, 15, 7, 29, 6, 1, 9, 30, 22, 5, 28, 18, 26, 11, 2, 14, 16, 12]

# Rearrange the original rank based on the given arrangement
reordered_rank = ''.join([original_rank[i] for i in arrangement])
print(reordered_rank)

```

### Step 4: Run the Script
- Running the script produced the reordered string.
- The final flag was then wrapped in the required format: `wgmy{reordered_string}`.


