# What Is a CLI?

A beginner-friendly introduction to command-line interfaces for non-technical users.

---

## The Short Answer

A **CLI** (Command-Line Interface) is a way to control your computer by typing text commands instead of clicking with a mouse.

You've probably seen it in movies—the black screen with green or white text where hackers type rapidly. In reality, it's much more mundane and incredibly useful.

---

## Why Should You Care?

You might be thinking: *"I've used computers my whole career without ever needing this. Why start now?"*

Here's the thing: **AI coding assistants like Claude Code run in the CLI.** If you want to use the most powerful version of Claude—one that can actually read your files, create documents, and automate your work—you need to be comfortable with basic CLI concepts.

The good news? You don't need to become an expert. You just need to know enough to:
1. Open the terminal
2. Navigate to a folder
3. Run Claude Code

That's about 5 commands total.

---

## GUI vs CLI

You're already familiar with **GUIs** (Graphical User Interfaces):

| Task | GUI Approach | CLI Approach |
|------|--------------|--------------|
| Open a folder | Double-click the folder icon | Type `cd folder-name` |
| See what's inside | Look at the icons | Type `ls` |
| Create a file | Right-click → New → File | Type `touch filename` |
| Delete a file | Drag to trash | Type `rm filename` |

> **Windows:** Use `dir` instead of `ls`.

**Why would anyone use the CLI way?**

1. **Speed** — Once you know the commands, typing is faster than clicking
2. **Automation** — You can save commands as scripts that run automatically
3. **Power** — Some things can only be done via CLI
4. **AI tools** — Claude Code and similar tools require CLI access

---

## What Is a Terminal?

The **terminal** (also called "command line," "console," or "shell") is the application where you type CLI commands.

On Mac, it's called **Terminal** (in Applications → Utilities, or search with Spotlight).

When you open it, you'll see a blank window with a **prompt**—a line of text waiting for your input:

```
yourname@computer ~ %
```

This is just telling you where you are in your file system. Think of it like the address bar in Finder.

> **Windows:** The terminal is called PowerShell. The prompt looks like `C:\Users\YourName>`.

---

## The 5 Commands You Actually Need

Here's everything you need to know to use Claude Code:

### 1. `pwd` — Where am I?

"Print Working Directory" — shows you your current location.

```
pwd
```

Output might be: `/Users/yourname/Documents`

This is like looking at the folder path at the top of a Finder window.

---

### 2. `ls` — What's here?

Lists all files and folders in your current location.

```
ls
```

Output:
```
Documents
Downloads
Desktop
my-project
report.xlsx
```

> **Windows:** Use `dir` instead.

---

### 3. `cd` — Go somewhere

"Change Directory" — moves you to a different folder.

```
cd Documents
```

Now you're inside the Documents folder.

**Go back up one level:**
```
cd ..
```

**Go to your home folder:**
```
cd ~
```

---

### 4. `claude` — Start Claude Code

Once installed, this launches Claude Code.

```
claude
```

That's it. Now you're talking to Claude in your terminal, and it can see and edit your files.

---

### 5. `exit` — Leave

Closes the terminal or exits a program.

```
exit
```

---

## A Simple Exercise

Let's practice. This will take about 2 minutes.

1. Press `Cmd + Space`, type "Terminal", press Enter
2. You'll see a window with a prompt
3. Type `pwd` and press Enter — this shows where you are
4. Type `ls` and press Enter — this shows what's in that folder
5. Type `cd Desktop` and press Enter — now you're on your Desktop
6. Type `ls` and press Enter — you'll see your Desktop files
7. Type `cd ~` and press Enter — back to your home folder

**Congratulations!** You just used the command line.

> **Windows:** Press the Windows key, type "PowerShell", press Enter. Use `dir` instead of `ls`.

---

## Common Fears (Addressed)

### "What if I break something?"

You won't. The commands you'll use are safe. The worst case is you get an error message like "file not found" or "command not recognized." Just try again.

### "It looks complicated"

It's simpler than it looks. The movies show hackers typing 100 words per minute with green text. In reality, you'll type maybe 10 words total to start Claude Code.

### "I'll never remember the commands"

You only need 4-5 commands, and you'll use them repeatedly. They'll become muscle memory quickly. Plus, Claude Code itself can help you—just ask "how do I navigate to my Documents folder?"

### "Why can't AI tools just have a normal app?"

They're getting there, but CLI tools are currently more powerful. Think of it like learning to drive a manual transmission—a little more effort upfront, but more control and capability.

---

## Key Terminology

| Term | What It Means |
|------|---------------|
| **CLI** | Command-Line Interface — text-based computer control |
| **GUI** | Graphical User Interface — visual, click-based control |
| **Terminal** | The application where you type commands |
| **Shell** | The program that interprets your commands |
| **Command** | An instruction you type |
| **Directory** | Same as a folder |
| **Path** | The location of a file or folder (like an address) |
| **Prompt** | The text that appears before your cursor, waiting for input |

---

## You're Ready

That's all the CLI knowledge you need to get started with Claude Code.

**Next step:** Head to [Getting Started with Claude Code](GETTING-STARTED-CLAUDE-CODE.md) to install and configure the tool.

---

[← Back to Overview](../README.md)
