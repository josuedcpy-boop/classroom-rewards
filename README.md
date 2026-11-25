# Classroom Rewards — The Store

A classroom reward system that runs in your web browser. Students earn points for good work and behavior, spend them on rewards you choose (like a homework pass or music day), and can try their luck on fun prize wheels. You can also take points away when needed.

Everything lives in **one file**: `point_store.html`. There is nothing to install, no account to create, and no internet connection needed.

---

## Table of contents

1. [Getting started (5 minutes)](#1-getting-started-5-minutes)
2. [The big idea: how points work](#2-the-big-idea-how-points-work)
3. [Setting up your class](#3-setting-up-your-class)
4. [The Store tab](#4-the-store-tab)
5. [Giving and taking points](#5-giving-and-taking-points)
6. [The Prize Wheel tab](#6-the-prize-wheel-tab)
7. [Holiday and special modes](#7-holiday-and-special-modes)
8. [Random Student picker](#8-random-student-picker)
9. [Saving your work and backups (important!)](#9-saving-your-work-and-backups-important)
10. [Using it on another computer](#10-using-it-on-another-computer)
11. [Frequently asked questions](#11-frequently-asked-questions)
12. [For people who want the technical details](#12-for-people-who-want-the-technical-details)

---

## 1. Getting started (5 minutes)

1. **Download the file.** On this GitHub page, click `point_store.html`, then click the **Download raw file** button (the arrow pointing down, near the top right of the file view). Or click the green **Code** button → **Download ZIP** and unzip it.
2. **Put it somewhere you'll remember**, such as your Documents folder. Keep it in the same place from now on (see [why](#9-saving-your-work-and-backups-important)).
3. **Double-click the file.** It opens in your web browser (Chrome, Edge, Firefox or Safari all work). That's it. The app is running.

The first time you open it, you'll see:

- A grade called **Test Grade**
- A student called **Test Student** with **100 points**
- A sample list of rewards in the shop

These are just examples so you can play around and see how everything works. Try buying something with Test Student, spin the wheel, give and take points. When you're ready, rename or delete them and add your real class (see [Setting up your class](#3-setting-up-your-class)).

> **Tip:** Bookmark the page in your browser so you can reopen it with one click.

---

## 2. The big idea: how points work

Think of it like a classroom bank account for each student:

- **Every student has a balance** — the number of points they have right now.
- **You give points** for good things (participation, finishing work, kindness…).
- **Students spend points** in the Store on rewards. When they buy something, it goes into their **inventory** (their "backpack" of things they own but haven't used yet).
- **You can take points away** for bad behavior. Students **can go below zero** — that's "debt". If a student is at −30 and earns 10 points, they're at −20. They need to pay off their debt before they can buy things again.
- **Prize wheels** let students win extra points or items by chance.

---

## 3. Setting up your class

Click **👥 Manage Students** at the top. This turns on "edit mode" for students and grades: pencils, ✕ buttons and dropdowns appear. Click it again when you're done.

### Grades (classes)

Grades are how you group students, for example "5th", "6th", "7th", or "Period 1", "Period 2".

- **Add a grade:** click **+ Add Grade** and type the name. Type just "5th", not "5th Grade" — the app adds the word "Grade" for you.
- **Rename a grade:** click the ✏️ pencil next to it. Students in that grade move with it automatically.
- **Delete a grade:** click the ✕ next to it. Two safety rules: the grade must be **empty** (move or remove its students first), and you always need **at least one** grade — so add your real grades *before* deleting "Test".

### Students

- **Add a student:** click the **+ Add Student** card. A new student called "New Student" appears in whichever grade you're currently viewing. Click on the name to type the real one, then press **Enter**.
- **Set a balance directly:** in edit mode you can click the number of points on a student's card and type a new amount (handy when moving over from a paper system).
- **Change a student's grade:** use the grade dropdown on their card.
- **Remove a student:** click the ✕ on their card. You'll be asked to confirm. ⚠️ Their points and inventory are deleted with them.
- **Filter by grade:** the grade buttons above the student list (**All**, **5th Grade**, etc.) show only that class. This filter also applies on the wheel tab.

### Suggested first-day setup

1. Add your real grades (e.g. 5th, 6th, 7th).
2. Delete Test Student, then delete the "Test" grade.
3. Add your students.
4. Review the rewards in the shop (next section) and change prices to fit your class.
5. Click **💾 Save**, then **⬇️ Export File** to make your first backup.

---

## 4. The Store tab

This is the main screen.

### Choosing who is shopping

Click a student's card. It gets highlighted and a banner shows **"Shopping as [name]"** with their balance. Everything you do in the shop now happens for that student.

### Buying a reward

Each reward card shows its **cost**. Click **Buy**. The points come out of the student's balance and the item goes into their inventory. If the student can't afford it (or is in debt), the Buy button is greyed out.

### The inventory (what a student owns)

Below the shop you'll see the selected student's inventory, with how many of each item they have:

- **Use one** — the student cashes in the reward (e.g. they hand in their Late Work Pass). It's removed from their inventory.
- **Return & refund** — undo a purchase: the item is removed and the points go back.

### Editing the shop

Click **✏️ Edit Store**. Now you can:

- Change any reward's **name, price, or note** by clicking on it and typing.
- **Add** new rewards.
- **Remove** a reward with its ✕.

Click the button again to stop editing.

**The starting rewards** are only examples (bonus points, Spotify music for a week, Homework Pass, Late Work Pass, a "Cheater pass" for one bit of help from the teacher, a gift card…). Change them to whatever works in your classroom.

---

## 5. Giving and taking points

There are several ways:

| What you want | How |
|---|---|
| Give/take points for **one student** | Click the 🎁 button on their card (or **🎁 Give Points** in the "Shopping as" banner). Type a positive number to give, a negative number (like `-10`) to take. |
| Give/take points for a **whole grade or everyone** | Click **🎁 Give Points to All** at the top, pick a grade (or "All Grades") and the amount. |

### The "Points Taken" log

Every time points are taken away, it's written down. Click **📉 Points Taken** to see who lost points, how many, and when — with a total for each day. Useful for talking with students or parents. **Clear Log** empties it.

---

## 6. The Prize Wheel tab

Click **🎡 Prize Wheel** at the top. Select a student, then click **SPIN**.

### Normal wheel

The everyday wheel. Out of the box it has: Nothing, 5, 10, 20, 50 points, Try Again, and a 100-point Jackpot. Each prize has a **% chance** (how often it comes up). The wheel shows colors only, so students can't read where it will stop.

### Lucky Wheel

Sometimes a spin turns into a **Lucky spin** with much better prizes (50, 100, 250 points, or a Mystery Prize). By default this happens **10% of the time**. You can change that %.

### Risk It

After winning, a student can choose to **Risk It**:

- It's a coin flip — **50% win, 50% lose**.
- **Win:** they spin again and the winnings stack up. Example: win 10, risk, win 10 → they now have 30 on the line.
- **Lose:** they lose what they'd won in that streak. They **never** lose points they already had before spinning.
- They can stop any time and keep what they've won.

### Editing prizes

Click **✏️ Edit Prizes** to:

- Change a prize's name, how many points it gives, and its **% chance**.
- Change a slice's **color** (↺ puts the original color back).
- **+ Add Prize** or remove prizes.
- Make a prize give a **shop item** instead of points (it goes straight into the winner's inventory).
- Use **Random Item** as a prize: the app picks a random reward from your shop, and **cheaper items are more likely** than expensive ones. Click **🎲 Random Item Odds** to see the chances.

Use the small tabs (Normal Wheel, Lucky Wheel, etc.) to choose which wheel you're editing.

---

## 7. Holiday and special modes

Only **one** special mode can be on at a time. Turning one on turns the others off. Turn them on with the buttons on the Prize Wheel tab.

### 🎃 Halloween Mode

The wheel becomes a spooky wheel with:

- **Candy** (a special item worth 50 points), Pumpkin, Bat, and Spooky Jackpot prizes, up to a **200-point MEGA JACKPOT**.
- **🕷️ Stuck in the web:** the student loses everything won *in that spin streak*. Those points go into the **Web Stash**.
- **🕸️ Web Stash:** a growing pot of points the web has "eaten". Landing on the Web Stash slice wins the whole pot. Click the Web Stash button to see or change the amount.
- **Trick or Treat doors:** some spins let the student pick a door. Behind it could be:
  - **Treat** — candy or 1–100 bonus points
  - **Trick** — their winnings go to a random classmate in the same grade
  - **Rare door** — candy for them *and* 4 classmates
  - **Lose everything**, **lose 1–100 points**, **spin again**, or **nothing**
- Click **🚪 Door Odds** to change how likely each door is.

### 🎄 Christmas Mode

A whole holiday event:

- **Class Christmas trees** — each grade has its own tree. Winning an **Ornament** adds one to the class tree. When the tree reaches certain numbers (10, 25, 50 ornaments by default), **the whole class** gets a reward (points, a free-choice day, a class party…). Everyone works together.
- **Snowmen** — each student builds their own snowman by collecting 5 pieces (hat, carrot nose, scarf, buttons, eyes). Finishing one gives a reward (100 points by default) plus a **Christmas Miracle** roll: a chance of a present, Hot Cocoa, or an Elf Helper.
- **Presents** — the student picks one of three presents. Inside could be an ornament, a snowman piece, candy, a buff, a random shop item, or a **Store Points Jackpot (100–1000 points)**. Extremely rarely (0.1%) it's the **Ultimate Christmas Present: "Skip the Final Test"** — an item that can only be won this way.
- **Buffs (power-ups):**
  - **☕ Hot Cocoa** — +10 extra points on the student's next 3 wins. Works automatically.
  - **✨ Elf Helper** — doubles a Christmas prize. The student saves it and is asked if they want to use it after winning something.

Click **🎁 Christmas Settings** to change the snowman reward, tree milestones, snowman pieces, and Miracle odds.

### 😈 Naughty Wheel

A punishment wheel for serious misbehavior. **Every slice has the same chance.**

- One slice is **"Saved"** — nothing happens.
- Other slices take away a **flat amount** (10, 25, 50, 75, or 100 points) or a **percentage** of the student's balance (10%, 20%, 30%, or 50%).
- Students can go into debt. A percentage slice does nothing if the student already has 0 or fewer points.
- You're asked to **confirm before spinning**, and there's an **Undo** button afterwards in case of a mistake.

---

## 8. Random Student picker

Click **🎲 Random Student**, choose a grade, and click **Roll**. It picks a student at random — great for "who answers next?".

- It **won't pick the same student twice** until everyone has been picked.
- **Reset Session** starts over so everyone can be picked again.
- **Select Student** makes the picked student the active one (for shopping or spinning).

---

## 9. Saving your work and backups (important!)

### How saving works

The app **saves automatically** in your web browser as you work. The **💾 Save** button saves right away if you want to be sure.

The data is stored **inside that browser on that computer** — not online, not in the file itself. This means:

- ✅ Your students' names never leave your computer.
- ⚠️ If you **clear your browser history/data**, use a **different browser**, use **private/incognito mode**, or **move the file to another folder**, the app will start fresh with Test Student again — your data won't be there.

### Make backups

Click **⬇️ Export File**. It downloads a small backup file (ending in `.json`) with all your students, points, rewards, and settings. **Do this regularly** — for example every Friday — and keep the backups somewhere safe (a USB drive, Google Drive, OneDrive…).

To restore a backup, click **⬆️ Import File** and choose the backup file. **This replaces everything currently in the app** with what's in the backup.

### Printing

**🖨️ Print** prints the current screen — for example the Store tab as a reward menu to post in the classroom.

---

## 10. Using it on another computer

1. On the old computer: click **⬇️ Export File**.
2. Copy `point_store.html` and the backup file to the new computer (email, USB, cloud drive).
3. On the new computer: open `point_store.html`, click **⬆️ Import File**, choose the backup.

Everything — students, points, inventories, rewards, settings — is now on the new computer.

---

## 11. Frequently asked questions

**Do I need internet?**
No. Once you have the file, it works completely offline.

**Is it free? Do students need accounts?**
Yes it's free, and no — only the teacher uses it, usually on the classroom computer or projector.

**Can students see each other's points?**
If it's on the projector, yes. Use the grade filter so only one class shows at a time.

**I opened it and my students are gone!**
Usually because you opened it in a different browser, in private mode, or the file was moved. Open it the way you normally do, from the same place. If it's really gone, use **⬆️ Import File** with your latest backup.

**A student bought something by accident.**
Select the student, find the item in their inventory, and click **Return & refund**.

**I took too many points by mistake.**
Give the points back with 🎁 (a positive number). On the Naughty Wheel, use **Undo**.

**Can I change the % chances of everything?**
Yes — all wheels, doors, presents, and Christmas settings are editable.

**Can I share this with another teacher?**
Yes, send them `point_store.html` (or the link to this GitHub page). **Don't send them your backup file** unless you want them to have your students' names and data.

---

## 12. For people who want the technical details

- Single HTML file, plain JavaScript and CSS. No frameworks, build step, server, or dependencies.
- State is stored in the browser's `localStorage` under the key `pointStoreData_v2`. Export/Import uses a JSON file of the same state.
- Fresh installs (no saved data) start with the `Test` grade and `Test Student` (see `DEFAULT_GRADES` and `DEFAULT_STUDENTS` in the file).
- Development history, data model, and function reference: see [CONTEXT.md](CONTEXT.md).

### Privacy note

Student names live only in your browser. **Never commit exported `.json` backups to a public repository** — the `.gitignore` file in this project already blocks `.json` files to help prevent that.
