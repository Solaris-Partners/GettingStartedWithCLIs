# Plan Mode: Think Before You Build

**This guide explains Plan Mode—a way to make Claude think through a problem before making changes.**

If you've used Claude Code and watched it start editing files immediately, you know it can sometimes go in the wrong direction. Plan Mode fixes this. It forces Claude to research and create a plan *first*, and only make changes *after* you've approved the approach.

---

## Why Plan Mode Matters

Without Plan Mode, here's what often happens:

1. You ask Claude to add a feature
2. Claude immediately starts editing files
3. You realize it's doing something different than what you wanted
4. You have to undo everything and start over

With Plan Mode:

1. You ask Claude to add a feature
2. Claude researches your codebase and writes a plan
3. You read the plan and say "actually, do it this other way"
4. Claude updates the plan
5. You approve, and *then* Claude makes the changes

**The key insight:** It's much easier to fix a plan than to fix code that's already been written.

---

## How to Turn On Plan Mode

While Claude Code is running, press **Shift+Tab** to cycle through modes:

| Mode | Indicator at bottom | What it means |
|------|---------------------|---------------|
| Normal | (nothing special) | Claude asks permission for each action |
| Auto-Accept | `⏵⏵ accept edits on` | Claude makes edits without asking |
| Plan Mode | `⏸ plan mode on` | Claude can only research and plan—no edits |

So to get to Plan Mode from Normal Mode, press **Shift+Tab twice**.

To exit Plan Mode, press **Shift+Tab again** (it cycles back to Normal).

---

## The Planning Workflow

Here's the recommended four-phase approach:

### Phase 1: Explore

Tell Claude what you want to understand. In Plan Mode, Claude will read files and explain things without changing anything.

```
Look at the files in /src/auth and explain how user login works.
What files would I need to change to add a "forgot password" feature?
```

Claude will read through your code and give you an explanation.

### Phase 2: Plan

Ask Claude to create a detailed plan for what you want to build.

```
I want to add a "forgot password" feature. Create a plan for how to implement this.
What files need to change? What's the step-by-step approach?
```

Claude will produce a numbered list of steps, explaining:
- Which files need to be created or modified
- What order to make the changes
- Any dependencies or considerations

### Phase 3: Refine the Plan (This Is the Important Part)

**Don't just accept the first plan.** This is where most people go wrong.

Read through the plan carefully. Then ask follow-up questions:

- "What about users who try to reset their password multiple times?"
- "How long should the reset link be valid?"
- "Should we send an email confirmation after the password is changed?"

Each time you ask, Claude will update the plan. Keep refining until you're confident the plan matches what you actually want.

**You can also edit the plan directly:** Press **Ctrl+G** to open the plan in a text editor, make your changes, and save. Claude will use your edited version.

### Phase 4: Implement

Once you're happy with the plan, exit Plan Mode (press Shift+Tab) and tell Claude to implement it:

```
Implement the plan you just created.
```

Claude will now make the actual changes, following the plan you approved.

---

## The "Clear Context and Proceed" Menu

After you approve a plan, Claude shows you a menu with options:

```
Would you like to proceed?

❯ 1. Yes, clear context and auto-accept edits
  2. Yes, and manually approve edits
  3. Yes, auto-accept edits
  4. Yes, manually approve edits
  5. Type here to tell Claude what to change
```

### What These Options Mean

| Option | What happens |
|--------|--------------|
| **1. Clear context and auto-accept** | Recommended. Clears the conversation history (but keeps the plan), then implements without asking about each edit |
| **2. Clear context and manually approve** | Clears history, but asks you to approve each individual edit |
| **3. Auto-accept edits** | Keeps conversation history, implements without asking |
| **4. Manually approve edits** | Keeps history, asks about each edit |
| **5. Type to change** | Go back to refining the plan |

### Why "Clear Context" Is Usually Best

When you've been planning for a while, your conversation gets long. Claude has a limited memory (called the "context window"), and a long planning conversation uses up that memory.

By clearing the context:
- Claude keeps your approved plan
- Claude forgets the back-and-forth discussion
- Claude has maximum memory available to actually implement the plan

**This helps Claude stay focused and follow the plan more accurately.**

Think of it like this: if you give someone a detailed instruction manual, they don't also need the transcript of every conversation you had while writing that manual. They just need the final instructions.

---

## When to Use Plan Mode

**Start in Plan Mode by default.** This should be your normal workflow for anything beyond trivial changes.

The only time to skip Plan Mode is when:
- It's a tiny feature (fixing a typo, changing a color, one-line fix)
- You know *exactly* what you want and how it should be done

If there's any ambiguity—if you're not 100% sure how the code should work or where changes need to happen—start in Plan Mode. It's always easier to approve a good plan quickly than to undo bad code.

---

## Tips for Better Plans

### Be Specific About What You Want

Instead of:
```
Add user authentication
```

Try:
```
Add user authentication using email and password. Users should be able to:
- Sign up with email/password
- Log in
- Log out
- Reset their password via email
```

The more detail you provide upfront, the better the initial plan will be.

### Ask "What About..." Questions

After Claude generates a plan, challenge it:

- "What about error handling?"
- "What about users on slow connections?"
- "What about security—is this approach safe?"

These questions help Claude think through edge cases.

### Use Deeper Thinking Keywords

When you want Claude to really think through something, use these phrases:

- "think" — normal analysis
- "think hard" — more thorough
- "think harder" — even more thorough
- "ultrathink" — maximum analysis

For example:
```
Think hard about this plan. Are there any edge cases we're missing?
```

### Keep Plans Focused

Don't try to plan your entire project at once. Plan what you can accomplish in one sitting. Then:

1. Plan → Implement → Test → Commit
2. Plan the next piece → Implement → Test → Commit

Small, focused plans are easier to review and more likely to succeed.

---

## Common Mistakes to Avoid

### Mistake 1: Accepting the First Plan

The first plan is a starting point, not a final answer. Always read it carefully and ask at least one or two clarifying questions.

### Mistake 2: Not Reading the Plan Before Proceeding

It's tempting to just click "proceed" and trust Claude. But the whole point of Plan Mode is to catch problems *before* they become code. Take the time to read.

### Mistake 3: Plans That Are Too Big

If a plan has more than 10-15 steps, it's probably too big. Break it into smaller pieces and implement them one at a time.

### Mistake 4: Skipping Clear Context

For long planning sessions, always use "Clear context and proceed." Keeping all that conversation history makes Claude more likely to get confused during implementation.

---

## Quick Reference

| What you want to do | How to do it |
|---------------------|--------------|
| Enter Plan Mode | Press **Shift+Tab** twice |
| Exit Plan Mode | Press **Shift+Tab** |
| Edit the plan directly | Press **Ctrl+G** |

---

## Summary

Plan Mode is about working smarter, not faster. Yes, it adds an extra step before Claude starts coding. But that step can save you hours of fixing code that went in the wrong direction.

The workflow:
1. **Enter Plan Mode** (Shift+Tab twice)
2. **Explore** — Let Claude understand your codebase
3. **Plan** — Get a detailed implementation plan
4. **Refine** — Keep improving the plan until it's right
5. **Clear context and proceed** — Give Claude a fresh start to implement
6. **Implement** — Watch Claude follow the plan you approved

The more complex your task, the more valuable Plan Mode becomes.

---

[← Back to Getting Started](GETTING-STARTED-CLAUDE-CODE.md) | [Advanced Guide →](ADVANCED.md)
