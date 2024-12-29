# World 2

## Challenge

<p align= "center">
  <img src="https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Game/World%202/world1.png" alt="Challenge Image">
</p>


The prompt provided an `APK` file of a game similar to **World 1**.

## Analysis & Solution

### Step 1: Identifying the Challenge Context
This was my first time tackling a game hacking challenge, but I had seen my friend approach **World 1**. The description gave a clear hint with "time to do it again," suggesting a similar approach could work.

The key difference was that this game was on a different platform, which added a new layer of difficulty.

### Step 2: Playing the Game
- I played the game for one round, saving the game after each session (a "round" involved fighting an opponent).
- Each round won provided me with a part of the flag.
- Each save generated an `rmmsave` file in the game’s directory, which became crucial later.

### Step 3: Overcoming Obstacles
**Obstacle 1: Missing Part of the Flag**
- The game provided four parts of the flag: Flag 1, Flag 2, Flag 3, and Flag 5. However, Flag 4 was missing.
- After some exploration and recalling my friend’s experience in **World 1**, I discovered that Flag 4 was hidden in the lava section of the game. It was written directly on the lava, requiring careful navigation to piece it together. Credit to my friend for noticing this in **World 1**. 

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Game/World%202/world2.png" alt="Challenge Image" width="490" height="450">
</p>

**Obstacle 2: Defeating the Final Boss**
- The final boss was unbeatable through regular gameplay—its attack dealt an absurd amount of HP damage. To overcome this, I modified the save file.
- I extracted the rmmsave file from the game folder and uploaded it to [Save Editor Online](https://www.saveeditonline.com/). This tool allowed me to edit the file’s attributes.
- I increased all critical stats (HP, attack, etc.) to atleast `1000000`, downloaded the modified file, and replaced the original in the game folder. After reloading the game, my character was now overpowered, capable of defeating the boss in one attack. 

<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Game/World%202/world4.png" alt="Challenge Image">
</p>

- After reloading the game, my character was now overpowered, capable of defeating the boss in one attack. 
<p align= "center">
  <img src = "https://github.com/batricha/CTF-Writeups/blob/main/WGMY2024/Game/World%202/world5.jpeg" alt="Challenge Image" width="490" height="450">
</p>

### Step 4: Capturing the Flag
- Defeating the final boss rewarded me with Flag 5. Combining all five flag parts gave the full flag.
- While the process was straightforward in hindsight, navigating the lava section to read Flag 4 was particularly challenging.




