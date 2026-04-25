# 🛡️ Code Guardian — Anti-Gravity Skill

**Strict behavioral guardrails for AI coding agents.**  
Prevents laziness, hallucination, incomplete work, and destructive edits.  
Designed for **non-coder users** who cannot verify AI output independently.

---

## The Problem

AI coding agents (Gemini, Claude, GPT, etc.) working inside IDEs like Anti-Gravity, Cursor, or Windsurf have a pattern of:

| Bad Behavior | Example |
|---|---|
| **Partial completion** | You ask for 10 fixes, it does 5 and says "Done!" |
| **Hallucination** | It reads 3 files, then guesses the contents of 20 others based on filenames |
| **Destructive edits** | While fixing Bug A, it rewrites an entire file and breaks Features B, C, and D |
| **Silent failures** | A command errors out, but the agent says "completed successfully" |
| **Scope creep** | You ask to fix a button color, it also "improves" your database schema |
| **Jargon overload** | "I refactored the singleton to use dependency injection" — what? |

**If you can't code, you can't catch these mistakes.** They ship to production silently.

---

## The Solution

Code Guardian is a **skill file** — a set of instructions that get injected into the AI's system prompt at the start of every conversation. It forces the AI to follow 10 strict rules:

| # | Rule | What It Prevents |
|---|---|---|
| 1 | **Complete All Tasks** | Doing 5/10 tasks and saying "done" |
| 2 | **Actually Read Files** | Guessing file contents from filenames |
| 3 | **Never Break Working Code** | Rewriting entire files when 3 lines need changing |
| 4 | **Show Your Work** | Invisible changes with no proof |
| 5 | **Scope Discipline** | Wandering off-task and "improving" things you didn't ask for |
| 6 | **Handle Errors Honestly** | Hiding failures or pretending things worked |
| 7 | **File Scanning Protocol** | Reading 3 files and claiming "I reviewed everything" |
| 8 | **Preserve Documentation** | Deleting comments and docs to "clean up" |
| 9 | **Version Safety** | Destructive operations without backup |
| 10 | **Plain English Communication** | Technical jargon a non-coder can't understand |

---

## Installation

### For Anti-Gravity IDE

Copy the `code-guardian` folder into your Anti-Gravity skills directory:

```
C:\Users\<YourUsername>\.gemini\antigravity\skills\code-guardian\
```

The folder structure should look like:

```
skills/
└── code-guardian/
    └── SKILL.md
```

**That's it.** The skill is automatically loaded into every new conversation.

### For Other AI IDEs (Cursor, Windsurf, etc.)

The `SKILL.md` file follows a universal format. You can adapt it for any AI IDE that supports custom instructions or system prompts:

1. Open the `SKILL.md` file
2. Copy its contents
3. Paste into your IDE's custom instructions / rules file (e.g., `.cursorrules`, `.windsurfrules`, etc.)

---

## How It Works

Skills don't add buttons or change your IDE interface. Instead, they **change the AI's behavior** by injecting rules into its system prompt.

**Before Code Guardian:**
> You: "Scan my project and fix all PHP errors"  
> AI: *reads 3 files, guesses 20 others* → "Done! I found and fixed 2 issues."

**After Code Guardian:**
> You: "Scan my project and fix all PHP errors"  
> AI: *opens and reads every file, shows progress tracker* → "Scanned 23 files. Found 7 issues across 4 files. Here's what each fix does in plain English, and here's how to verify each one."

---

## Contributing

This skill was born from real frustration. If you've experienced similar problems with AI coding agents, your improvements are welcome!

### How to Contribute

1. **Fork** this repository
2. **Edit** `code-guardian/SKILL.md` with your improvements
3. **Submit a Pull Request** with a clear description of what problem your change solves

### Ideas for Improvement

- Additional rules for specific frameworks (React, Laravel, WordPress, etc.)
- Better verification step templates
- Rules for specific AI models that have unique failure patterns
- Translations to other languages
- Integration guides for more IDEs

---

## License

MIT License — Use it, share it, improve it.

---

## Credits

Created by [Hobby-Coding-Cat](https://github.com/Hobby-Coding-Cat) using the [Anti-Gravity IDE](https://github.com/nicepkg/aide).

Inspired by the [WordPress Agent Skills](https://github.com/WordPress/agent-skills) project.