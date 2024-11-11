# InTercept

## Challenge

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RTWH4.0/Web/InTercept/intercept1.png" alt="Challenge Image">
</p>

Hint: The "Here" button is a register page. Sorry for the wrong styling. <br>

The website provided has both a register and login page. Attempting to register and log in normally returns a message stating that 'Only admins can see the flag!'


## Solution
### Step 1: Exploring the Register Page
- I started by examining the register page. Following the hint, I used the browser’s **Inspect** tool to look at the form elements on the page.

### Step 2: Finding the Hidden Input
- In the form section of the HTML, I noticed an extra `<input>` element with `type="hidden" name="role" value="user" `. This input wasn’t visible on the registration form and it suggest that the current user role is 'user'

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RTWH4.0/Web/InTercept/intercept4.png" alt="Challenge Image">
</p>

- To make this input visible, I removed `type="hidden"` in the HTML inspector, allowing a small text input box to appear below the password field.

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/RTWH4.0/Web/InTercept/intercept5.png" alt="Challenge Image">
</p>

### Step 3: Registering as Admin
- I then registered a new account and, in the new input field, I changed from **"user"** to **"admin"** as the value.
- After completing the registration, I logged in using the newly registered credentials.


## Flag
`UCC{c00l_W3b_right!!}`  
