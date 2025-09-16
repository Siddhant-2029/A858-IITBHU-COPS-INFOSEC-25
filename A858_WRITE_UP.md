# 🔍 A858 CTF Event Write-up

This repository contains the complete solution write-up for the **first-ever CTF event organized by COPS for freshers**, inspired by the famous case of the mysterious subreddit **A858**.

---

## 📌 Event Overview
- The challenge began with a registration link: [team-registration-a858.vercel.app](https://team-registration-a858.vercel.app/)  
  (shared in the Discord announcement channel).  
- After registration, we received credentials for login.  
- Along with the registration link, we were also provided with an **AAA.TXT file** containing a hint related to **ASCII values**.

---

## 🧩 Step 1: The AAA.TXT File
- We tried counting the number of `A`s before each new line.  
- This led us to a **Pastebin link**:  
  🔗 [https://pastebin.com/kKTxgzFn](https://pastebin.com/kKTxgzFn)  

At first, the page appeared blank, but on closer inspection, we realized it actually contained **spaces and tabs**.

---

## 🧩 Step 2: Spaces and Tabs Puzzle
- By analyzing the text, we considered the following mapping:
  - **Space = 0**  
  - **Tab = 1**  
- Example: `1000001 → 65 → A`  
- Converting line by line, we obtained characters.  
- Repeating this process for all lines revealed the subreddit:  
  🔗 [https://www.reddit.com/r/858A/](https://www.reddit.com/r/858A/)  

This is where the **real challenge** began: finding the **4 pieces of a QR code**.

---

## 🧩 Step 3: Finding QR Code Fragments

### 🔹 QR Piece 2
- Found in a Reddit post titled **“Messi better”**.  
- In the comment section, the profile picture of user **Impossible_Fee7948** contained the QR code fragment.  
- This was relatively easy to spot.  

---

### 🔹 QR Piece 3
- Found in a Reddit post titled **“Help needed”**, which showed a picture of a screen.  
- In that post, we noticed another subreddit mentioned: **Ali3n1nva5i0n**.  
- Opening that subreddit, we found a post titled **“There you go”**, which directly contained **QR Piece 3**.  
- This one was straightforward once the subreddit was identified.  

---

### 🔹 QR Piece 1
This was one of the trickiest parts.  

1. In a Reddit post titled **“Found a new cipher! The game of secrets just got fishy”**, we were given a **Python code snippet** that could decode encoded text.  
   - It required:
     - A **secret key**
     - A **cipher text**  
   - Additionally, we had to run:  
     ```
     pip install pycryptodome
     ```

2. The cipher text was found in a Reddit post titled **“My brain is fried”**, in the comment section:CgOiYQ12hKFiQcpJiE4V08xoelFOd+922MFAUmKaxJi8djjO8lo5ezQgVO1OCs6+uKho9tGUJdlu9tIi9pHW5CFOquSZOTvQ/7AAiNl0/BkHN/IdnN4qXMaqfeDeb5+M0ezh0cjTdjZEGrySeyAo368ptDYqPkY2QLTRZoqcYho51m+us82aF/Ywoe1g7/JH

3. For the **secret key**, we referred to another Reddit post titled **“Just saw this movie and it’s crazy. Who’s gonna join me for a second run??”**.  
- The post hinted that **passwords and keys are A585**, but this didn’t work.  
- After several smart guesses, we discovered the actual key was **A858**.  

4. Running the program with this key successfully decrypted the text and revealed a **Google Drive link** with a message.  

5. Inside the Google Drive, we found a **photo**.  
- The background showed a **tree near one of the grounds of IIT BHU**.  
- We went to the spot, found the tree, and saw the QR code pasted on it.  
- Scanning it gave us **QR Piece 1**.  

This was already a tough challenge, but it got even harder with the last piece.  

---

### 🔹 QR Piece 4
The hardest fragment to obtain.  

1. After re-checking several Reddit posts, we carefully examined **all pictures and videos**.  
2. In a Reddit post titled **“I love 4Chan”**, a comment stated:  
- *“There is a clan which gives whatever you want.”*  
- The clan code was: **#2RYLCYCYG**.  
- It also referenced **CoC (Clash of Clans)**.  

3. We joined the clan using the code.  
- In the **guild chat**, someone commented: *“Demon Slayer is op”*.  
- This hinted at checking a **Demon Slayer video**.  

4. From the video, we extracted **longitude coordinates**:  25° 15′ 45.6″


5. To find the latitude, we revisited the **clan description**, where it was directly provided.  

6. Combining longitude and latitude pointed us to a location **near the jet in our campus**.  
- On reaching the location, we found the **last QR piece (QR 4)**.  

---

## 🧩 Step 4: Assembling the QR Code
- Once we had all **four QR fragments**, we stitched them together to form a **complete QR code**.  
- Scanning this QR redirected us to a **website**.  
- On the site, we received a **string** which we had to upload back to the same site (linked via the subreddit dashboard).  

---

## 🏁 Final Outcome
- All tasks were completed successfully.  
- We solved multiple layers of puzzles (ASCII, binary, cipher, coordinates, clan chat).  
- By combining the QR code fragments, we reached the final website and submitted the answer.  

✔️ **Event completed successfully!**

---

## 🛠️ Tools & Skills Used
- ASCII & binary conversion  
- Python (with `pycryptodome`)  
- Reddit clue hunting  
- QR code scanning  
- Google Drive exploration  
- Clan chat exploration (Clash of Clans)  
- Real-world coordinate puzzle-solving  

