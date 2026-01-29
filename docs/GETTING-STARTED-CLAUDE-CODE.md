# Getting Started with Claude Code

**This guide is for someone who has never used the command line before.**

You may have been using Claude through the website (claude.ai) or the desktop app. That's great for conversations, but **Claude Code** is different—it runs in your terminal and can actually read, write, and edit files on your computer.

---

## What You'll Need

- A Mac (or Windows PC—see notes throughout)
- About 30 minutes
- A Claude Max subscription ($100/month) — required for Claude Code

---

## Step 1: Open Your Terminal

1. Press `Cmd + Space` to open Spotlight
2. Type `Terminal`
3. Press Enter

You should see a window with a blinking cursor. This is your terminal.

> **Windows:** Press the Windows key, type `PowerShell`, and click on Windows PowerShell. Consider installing [Windows Terminal](https://aka.ms/terminal) for a nicer experience.

---

## Step 2: Install Node.js (Required First)

Claude Code needs Node.js to run.

1. Go to: **https://nodejs.org**
2. Download the **LTS** version (the big green button)
3. Run the installer, click Continue through everything
4. Close and reopen your terminal

**Verify it worked:** Type this and press Enter:
```
node --version
```

You should see something like `v20.x.x`. If you see an error, restart your computer and try again.

---

## Step 3: Install Claude Code

In your terminal, type this command and press Enter:

```
npm install -g @anthropic-ai/claude-code
```

Wait for it to finish (may take a minute). You'll see some text scroll by—that's normal.

---

## Step 4: Make Sure You Have the Right Plan

**IMPORTANT:** Claude Code requires a paid Anthropic plan.

You need **Claude Max** ($100/month) or higher.

1. Go to: **https://claude.ai/settings/billing**
2. Make sure you're on the Max plan

The Pro plan with API access works differently and isn't covered in this guide.

---

## Step 5: Start Claude Code and Log In

In your terminal, type:

```
claude
```

The first time you run it, Claude Code will ask you to authenticate.

**DO NOT use an API key.** Instead:
1. Choose the option to **log in with your Claude account**
2. It will open a browser window
3. Log in with your Anthropic account (the same one you use for claude.ai)
4. Authorize the connection

Once authenticated, you'll see Claude Code ready to chat in your terminal.

---

## Step 6: Set Up Dangermode (Recommended)

By default, Claude Code asks for permission before every action—running commands, editing files, etc. This gets tedious fast.

**Most people run Claude Code with "dangermode" enabled.** This lets Claude work without constantly asking for approval.

1. Open your shell profile:
   ```bash
   nano ~/.zshrc
   ```

2. Add this line at the bottom:
   ```bash
   alias ccd='claude --dangerously-skip-permissions'
   ```

3. Press `Ctrl+X`, then `Y`, then Enter to save
4. Restart your terminal or run `source ~/.zshrc`

Now instead of typing `claude`, just type `ccd` and Claude will run without asking for permission on every action.

**Why "dangerously"?** The flag name sounds scary, but it's just Anthropic being cautious. In practice, Claude is safe and this is how most people use it. You're trusting Claude to run commands and edit files—which is the whole point of Claude Code.

> **Windows:** Open PowerShell and run `notepad $PROFILE`. Add this line: `function ccd { claude --dangerously-skip-permissions $args }`. Save and restart PowerShell. If the file doesn't exist, first run `New-Item -Path $PROFILE -ItemType File -Force`.

---

## Step 7: Try It Out

Now you're ready to use Claude Code. Here are some things to try:

**Ask Claude to create a file:**
```
Create a file called notes.txt with today's date and a reminder to review the quarterly report
```

**Ask Claude to read a file:**
```
Read the file on my Desktop called budget.xlsx and summarize the key figures
```

**Ask Claude to help with a task:**
```
I need to create a simple expense tracker spreadsheet. Can you help?
```

Claude will ask clarifying questions, create files, and show you what it's doing.

---

## Quick Reference: Terminal Basics

| What you want to do | Command |
|---------------------|---------|
| See where you are | `pwd` |
| List files in current folder | `ls` |
| Go into a folder | `cd folder-name` |
| Go up one folder | `cd ..` |
| Go to your home folder | `cd ~` |
| Clear the screen | `clear` |

> **Windows:** Use `dir` instead of `ls`, and `cls` instead of `clear`.

---

## Quick Reference: Claude Code Basics

| What you want to do | What to type |
|---------------------|--------------|
| Start Claude Code (with dangermode) | `ccd` |
| Start Claude Code (asks permission) | `claude` |
| Exit Claude Code | Type `/exit` or press `Ctrl+C` |
| Get help | Type `/help` |
| Clear conversation | Type `/clear` |

---

## What's the Difference from Desktop Claude?

| Feature | Claude Website/App | Claude Code CLI |
|---------|-------------------|-----------------|
| Chat with Claude | Yes | Yes |
| Read files on your computer | No | **Yes** |
| Edit/create files | No | **Yes** |
| Run terminal commands | No | **Yes** |
| Work inside your projects | No | **Yes** |

Claude Code is like having Claude sitting next to you at your computer, able to actually *do* things—not just talk about them.

---

## Troubleshooting

**"command not found: claude"**
- Close and reopen your terminal
- Make sure Node.js installed correctly (`node --version` should show a version)
- Try running `npm install -g @anthropic-ai/claude-code` again

**"You need to authenticate"**
- Run `claude` and follow the login prompts
- Make sure you're using your Claude account, not an API key

**"Permission denied" or access errors**
- You may need to prefix commands with `sudo`

> **Windows:** If you see "claude is not recognized," try the same fixes above. For permission errors, run PowerShell as Administrator (right-click → "Run as Administrator").

**Claude Code is slow or hangs**
- Check your internet connection
- Try restarting the terminal
- Run `/clear` to start a fresh conversation

---

## Next Steps

**Want Claude to plan first?** Learn about [Plan Mode](PLAN-MODE.md)—a way to make Claude think through problems before making changes. Highly recommended.

**Want to use GitHub?** Check out [Getting Started with GitHub](GETTING-STARTED-GITHUB.md) for a beginner-friendly guide.

**Curious about alternatives?** Read [Claude Code vs Codex](CLAUDE-CODE-VS-CODEX.md) to understand your options.

**Ready to build something?** Browse [Project Ideas](PROJECT-IDEAS.md) for practical things to create.

**Want more power?** The [Advanced Guide](ADVANCED.md) covers shortcuts and tools for power users.

---

## Need Help?

- Claude Code docs: https://docs.anthropic.com/claude-code
- Report issues: https://github.com/anthropics/claude-code/issues

---

[← Back to Overview](../README.md)
