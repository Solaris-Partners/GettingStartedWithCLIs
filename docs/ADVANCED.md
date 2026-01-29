# Advanced: Power User Guide

Once you're comfortable with the basics from the [Getting Started guide](GETTING-STARTED-CLAUDE-CODE.md), these tips will make you much faster.

Everything on this page is **optional**—but if you want to level up your terminal experience, keep reading.

---

## More Aliases

You already set up `ccd` for dangermode. Here are more shortcuts you can add.

Open your profile with `nano ~/.zshrc` and add:

```bash
# Basic shortcut
alias cc='claude'

# Start a new conversation
alias ccn='claude --new'

# Resume a previous conversation
alias ccr='claude --resume'

# Continue the most recent conversation
alias ccc='claude --continue'

# Dangermode (you probably already have this one)
alias ccd='claude --dangerously-skip-permissions'

# Dangermode + continue last session
alias ccdc='claude --dangerously-skip-permissions --continue'
```

After saving (`Ctrl+X`, then `Y`, then Enter), restart your terminal.

> **Windows:** Open PowerShell and run `notepad $PROFILE`. Use function syntax instead: `function cc { claude $args }`, `function ccn { claude --new $args }`, etc.

---

## CLI Tools That Make Terminal Life Better

These tools aren't required, but they make navigating your terminal much more pleasant. Install them with Homebrew (`brew install toolname`).

> **Windows:** Use `winget install` instead of `brew install`. See the Windows-specific commands below each tool.

---

### fzf - Fuzzy Finder

**What it does:** Lets you search through files, command history, and more with fuzzy matching. Start typing and it filters results in real-time.

```bash
brew install fzf
```

> **Windows:** `winget install junegunn.fzf`

**How to use:**
- Type `fzf` to search files in current directory
- Press `Ctrl+R` to search command history (once configured)

---

### zoxide - Smarter cd

**What it does:** Remembers directories you visit and lets you jump to them with partial names.

```bash
brew install zoxide
```

> **Windows:** `winget install ajeetdsouza.zoxide`

**Add to your profile** (`~/.zshrc`):
```bash
eval "$(zoxide init zsh)"
```

> **Windows:** Add to PowerShell profile: `Invoke-Expression (& { zoxide init powershell | Out-String })`

**How to use:**
```bash
# Instead of:
cd ~/Documents/work/projects/quarterly-reports

# Just type:
z quarterly
# or
z reports
```

It learns your habits and gets smarter over time.

---

### bat - Better file viewing

**What it does:** Like `cat` but with syntax highlighting and line numbers.

```bash
brew install bat
```

> **Windows:** `winget install sharkdp.bat`

**How to use:**
```bash
bat README.md
bat report.csv
```

---

### ripgrep (rg) - Faster Search

**What it does:** Search file contents blazingly fast.

```bash
brew install ripgrep
```

> **Windows:** `winget install BurntSushi.ripgrep.MSVC`

**How to use:**
```bash
# Find all files containing "revenue"
rg revenue

# Search only in specific file types
rg "Q1" --type csv

# Case insensitive
rg -i "budget"
```

---

### tldr - Simplified Help

**What it does:** Shows practical examples for commands instead of dense documentation.

```bash
npm install -g tldr
```

**How to use:**
```bash
tldr tar
tldr git commit
tldr curl
```

---

## Terminal Upgrades

### iTerm2 (Mac)

The default Terminal is fine, but iTerm2 has more features:
- Split panes
- Better search
- More customization

Download: https://iterm2.com

> **Windows:** Install Windows Terminal from the Microsoft Store for tabs, split panes, and better colors: https://aka.ms/terminal

---

### Oh My Zsh - Pretty Prompts

Customize your terminal prompt to show useful info.

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

> **Windows:** Use Oh My Posh instead: `winget install JanDeDobbeleer.OhMyPosh`, then add `oh-my-posh init pwsh | Invoke-Expression` to your PowerShell profile.

---

## All Claude Code Flags

| Flag | What it does |
|------|--------------|
| `--dangerously-skip-permissions` | Auto-accept all actions |
| `--new` | Start fresh conversation |
| `--resume` | Pick a previous conversation to continue |
| `--continue` | Continue the most recent conversation |
| `--model` | Choose a specific model |
| `--print` | One-shot mode, just print response and exit |
| `--help` | Show all available flags |

**Example - quick one-shot question:**
```bash
claude --print "What's the keyboard shortcut to select all text?"
```

---

## Keyboard Shortcuts in Terminal

| Shortcut | What it does |
|----------|--------------|
| `Ctrl+C` | Cancel current command / exit |
| `Ctrl+L` | Clear screen |
| `Tab` | Autocomplete file/folder names |
| `Up/Down` | Cycle through previous commands |
| `Ctrl+R` | Search command history |
| `Ctrl+A` | Jump to beginning of line |
| `Ctrl+E` | Jump to end of line |
| `Ctrl+W` | Delete word before cursor |
| `Ctrl+U` | Clear entire line |
| `Ctrl+K` | Delete from cursor to end of line |

> **Windows PowerShell:** Use `Home`/`End` instead of `Ctrl+A`/`Ctrl+E`, `Ctrl+Backspace` to delete words, and `Escape` to clear the line.

---

## Keyboard Shortcuts in Claude Code

While Claude Code is running, you can use these:

| Shortcut | What it does |
|----------|--------------|
| `Ctrl+C` | Cancel current operation |
| `/help` | Show available commands |
| `/clear` | Clear conversation history |
| `/exit` | Exit Claude Code |

---

## Full Recommended Setup

Here's everything in one block. Run `nano ~/.zshrc` and add:

```bash
# Claude Code aliases
alias cc='claude'
alias ccn='claude --new'
alias ccr='claude --resume'
alias ccc='claude --continue'
alias ccd='claude --dangerously-skip-permissions'
alias ccdc='claude --dangerously-skip-permissions --continue'

# Smart directory jumping (if zoxide is installed)
if command -v zoxide &> /dev/null; then
    eval "$(zoxide init zsh)"
fi

# Better aliases (if tools are installed)
if command -v bat &> /dev/null; then
    alias cat='bat'
fi
if command -v rg &> /dev/null; then
    alias grep='rg'
fi
```

Then restart your terminal.

> **Windows:** See the [Getting Started guide](GETTING-STARTED-CLAUDE-CODE.md) for PowerShell profile setup. The equivalent PowerShell configuration uses `function` syntax and `Set-Alias`.

---

## Tips for Power Users

1. **Use continue mode** — `ccc` or `ccdc` picks up where you left off
2. **Navigate with zoxide** — Stop typing long paths
3. **Search with ripgrep** — Find anything in seconds
4. **Learn keyboard shortcuts** — Small time savings add up
5. **Customize your prompt** — Make your terminal yours

---

## Need Help?

- Claude Code docs: https://docs.anthropic.com/claude-code
- Report issues: https://github.com/anthropics/claude-code/issues

---

[← Back to Overview](../README.md)
