# Inspector Gadget

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RTWH4.0/Forensics/inspector1.jpeg" alt="Challenge Image">
</p>

The log file contains web access logs capturing what appears to be an attempt at directory fuzzing.

## Solution
### Step 1: Initial Analysis of `access.log`
- The log contained numerous entries pointing to various directories, I scanned through to identify any patterns or significant information.


### Step 2: Searching for External Links
- Since the directories in the log didn’t reveal anything, I decided to search for external links that might have been referenced in the logs.
- **Command Used**: `strings access.log | grep '.com/'`
- This revealed an external link: 'https://pastebin.com/VYyGh28L'

### Step 3: Accessing the Link
- Visiting the Pastebin link, I found the hidden flag in plain text.


## Flag
`UCC{rtwh4.0 was fun init?}`  
