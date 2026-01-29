# Getting Started with GitHub

A super simple guide for non-technical users who've never used GitHub before.

---

## What Is GitHub?

Think of GitHub as **Google Docs for code and files**—but better.

- Multiple people can work on the same files
- Every change is tracked (you can always undo)
- Nothing gets lost or overwritten
- You can see who changed what and when

You don't need to be a programmer to use GitHub. Many teams use it for documentation, policies, and collaborative writing.

---

## Key Concepts (Plain English)

| Term | What It Actually Means |
|------|------------------------|
| **Repository (repo)** | A project folder. Contains all your files. |
| **Commit** | Saving your changes with a note about what you did. |
| **Push** | Uploading your saved changes to GitHub. |
| **Pull** | Downloading the latest changes from GitHub. |
| **Branch** | A separate copy where you can experiment without affecting the main version. |
| **Clone** | Copying a repo from GitHub to your computer. |

That's it. Those 6 terms cover 90% of what you'll do.

---

## Two Ways to Use GitHub

### Option A: The Website (Easiest)

You can do everything through github.com without installing anything:
- Read files
- Edit files (small changes)
- Upload files
- See change history

**Best for:** Browsing, small edits, reading documentation.

### Option B: From Your Computer (More Powerful)

Install the GitHub CLI tool to work with files locally:
- Edit files in your preferred apps
- Make bigger changes
- Work offline
- Use Claude Code to help

**Best for:** Regular contributors, larger projects, using Claude Code.

---

## Option A: Using the GitHub Website

### Viewing Files

1. Go to the repository URL (e.g., `github.com/company/project-name`)
2. Click on any file to read it
3. Click folders to navigate into them
4. Use the search bar to find specific files

### Editing Files Online

1. Navigate to the file you want to edit
2. Click the **pencil icon** (top right of the file content)
3. Make your changes
4. Scroll down to "Commit changes"
5. Write a brief description of what you changed
6. Click **Commit changes**

Done! Your changes are saved to GitHub.

### Creating New Files Online

1. In the repo, click **Add file** → **Create new file**
2. Type a filename (include the folder path if needed, like `docs/my-file.md`)
3. Write your content
4. Scroll down and commit with a description

### Uploading Files

1. In the repo, click **Add file** → **Upload files**
2. Drag and drop your files
3. Commit with a description

---

## Option B: Using GitHub from Your Computer

This method is more powerful and lets you use Claude Code to help with your work.

### Step 1: Install GitHub CLI

Open Terminal and run:

```bash
brew install gh
```

If you don't have Homebrew installed, install it first:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

> **Windows:** Open PowerShell and run `winget install GitHub.cli`, then restart PowerShell.

### Step 2: Log Into GitHub

In your terminal, run:

```
gh auth login
```

Follow the prompts:
1. Choose **GitHub.com**
2. Choose **HTTPS**
3. Choose **Login with a web browser**
4. Copy the one-time code shown
5. Press Enter to open GitHub in your browser
6. Paste the code and authorize

You're now connected.

### Step 3: Clone a Repository

"Cloning" copies a GitHub repo to your computer.

1. Navigate to where you want the project:
   ```
   cd ~/Documents
   ```

2. Clone the repo:
   ```
   gh repo clone owner/repo-name
   ```

   For example:
   ```
   gh repo clone mycompany/policies
   ```

3. Enter the project folder:
   ```
   cd repo-name
   ```

Now you have all the files on your computer.

### Step 4: Make Changes

Edit files however you like:
- Use any text editor (TextEdit, VS Code, etc.)
- Use Claude Code: just run `ccd` in the project folder

### Step 5: Save and Upload Your Changes

After making changes, you need to:

1. **Stage** your changes (tell Git what to save)
2. **Commit** them (save with a description)
3. **Push** them (upload to GitHub)

**The easy way—ask Claude Code:**
```
Commit my changes with a message describing what I did, then push to GitHub
```

Claude will handle all the steps for you.

**The manual way:**
```
git add .
git commit -m "Updated the expense policy document"
git push
```

### Step 6: Get the Latest Changes

Before starting work, always get the latest version:

```
git pull
```

This downloads any changes others have made.

---

## Common Tasks

### See What's Changed

```
git status
```

Shows files you've modified, added, or deleted.

### See Change History

```
git log --oneline
```

Shows a list of recent commits (changes).

### Undo Changes You Haven't Saved Yet

```
git checkout -- filename
```

Reverts a file to the last saved version.

### Create a Branch (Safe Experimentation)

```
git checkout -b my-experiment
```

Now you're on a separate branch. Changes here won't affect the main version until you merge them.

---

## Using Claude Code with GitHub

Once you've cloned a repo, Claude Code becomes incredibly powerful. Here's what you can do:

**Navigate to your project folder:**
```
cd ~/Documents/my-project
```

**Start Claude Code:**
```
ccd
```

**Ask Claude to help:**
- "What files are in this project?"
- "Show me the README"
- "Update the employee handbook to include the new PTO policy"
- "Create a new document called quarterly-goals.md"
- "Commit my changes and push to GitHub"

Claude handles all the Git commands for you. You just describe what you want in plain English.

---

## Troubleshooting

**"Permission denied" or "Authentication failed"**
- Run `gh auth login` again
- Make sure you're logged into the right GitHub account

**"Repository not found"**
- Check the spelling of the repo name
- Make sure you have access (ask your admin)

**"Your branch is behind"**
- Run `git pull` to get the latest changes
- If there are conflicts, ask Claude Code: "Help me resolve these Git conflicts"

**"Changes not showing on GitHub"**
- Make sure you committed AND pushed
- Run `git status` to see what needs to be done

---

## Best Practices

1. **Pull before you start** — Always run `git pull` before making changes
2. **Commit often** — Save your work in small chunks, not one giant change
3. **Write clear commit messages** — "Updated Q1 budget figures" is better than "changes"
4. **Don't commit sensitive data** — Keep passwords and API keys out of GitHub

---

## Need Help?

The best way to learn is to experiment. You can't really break anything—Git's history feature means everything can be undone.

When in doubt, ask Claude Code:
- "What's the current status of this Git repo?"
- "Help me push my changes to GitHub"
- "Explain what this Git error means"

---

[← Back to Overview](../README.md)
