---
name: prompt-auditor
description: Audit, clean, and optimize Claude setup files — including claude.md, skills, and context folders — to remove redundant, conflicting, vague, or outdated instructions. Use this skill whenever the user wants to audit their Claude setup, clean up their instructions, trim their claude.md, find conflicting rules, reduce prompt bloat, simplify their AI configuration, or asks why Claude isn't following their rules correctly. Also trigger when the user says things like "my setup feels bloated", "I have too many rules", "Claude keeps ignoring my instructions", or "help me clean up my prompts."
---

# Prompt Auditor

This skill helps users identify and remove dead weight from their Claude setup — the rules that contradict each other, repeat themselves, fix problems that no longer exist, or are too vague to be useful.

## The Core Problem

Over time, Claude setups accumulate rules reactively: one bad output → one new rule. After months of this, you end up with 30+ rules that:
- **Contradict each other** ("be concise" vs "always explain your reasoning")
- **Fix outdated problems** (the model already handles this by default now)
- **Repeat each other** across different files
- **Are too vague to follow consistently** ("be more natural", "use a good tone")

More rules ≠ better outputs. Extra instructions make Claude second-guess itself and dilute the rules that actually matter.

---

## The Audit Process

### Step 1: Read the full setup

Before doing anything else, read all the user's configuration files. In Claude Code or Cowork, you have direct access. Tell the user:

> "I'm going to read your full setup before auditing — give me a moment."

Then read:
- `claude.md` (or `CLAUDE.md`)
- Every file in the `skills/` folder
- Every file in the `context/` folder
- Any other instruction files you can find (`.cursorrules`, `system_prompt.txt`, etc.)

### Step 2: Evaluate every rule

For each rule or instruction found, assess it against these five criteria:

| # | Question | Flag if... |
|---|----------|-----------|
| 1 | **Default behavior?** Is this something Claude already does without being told? | Yes → candidate to cut |
| 2 | **Conflict?** Does this contradict or tension with another rule elsewhere? | Yes → flag both |
| 3 | **Redundant?** Is this already covered by another rule or file? | Yes → candidate to cut |
| 4 | **Reactive fix?** Does this read like it was added to fix one specific bad output? | Yes → candidate to cut |
| 5 | **Too vague?** Would Claude interpret this differently every time? | Yes → rewrite or cut |

### Step 3: Deliver the audit

Provide three outputs:

#### A. Cut List
Everything recommended to remove, with a one-line reason:
```
- "Always be professional" → vague; Claude does this by default
- "Explain technical terms" → conflicts with "be concise"; too context-dependent
- "Don't use bullet points for simple answers" → already covered in writing-style.md
```

#### B. Conflict Map
Any rules that fight each other across files:
```
⚠️  claude.md: "be concise" ↔ skills/writing.md: "always show your full reasoning"
⚠️  claude.md: "use casual tone" ↔ context/work.md: "maintain professional language"
```

#### C. Cleaned claude.md
A rewritten version of their `claude.md` with dead weight removed, conflicts resolved, and vague rules either sharpened or dropped.

---

## The Audit Prompt (for users running this manually)

If the user wants to run this themselves in Claude Code or Cowork, give them this prompt:

```
Read my entire setup before responding. Check my claude.md, every skill in my skills folder, every file in my context folder, and any other instruction files you can find.

Then go through every rule, instruction, and preference you found. For each one, tell me:

1. Is this something you already do by default without being told?
2. Does this contradict or conflict with another rule somewhere else in my setup?
3. Does this repeat something that's already covered by a different rule or file?
4. Does this read like it was added to fix one specific bad output rather than improve outputs overall?
5. Is this so vague that you'd interpret it differently every time? (e.g. "be more natural" or "use a good tone")

Then give me:
- A list of everything you'd cut with a one-line reason for each
- A list of any conflicts you found between files
- A cleaned-up version of my claude.md with the dead weight removed
```

---

## After the Audit: Validation Process

**Don't delete everything at once.** Guide the user through this process:

1. **Review** the flagged rules and reasons — do they make sense?
2. **Delete** the flagged rules from their setup
3. **Run** their 3 most common tasks with the trimmed setup
4. **Evaluate:**
   - Output same or better? → Deleted rules were dead weight ✓
   - Something specific broke? → Add back *just that one rule* ✓
5. **Repeat** until you've found the minimum viable setup

**Goal:** The simplest setup that produces the outputs they want. A good setup gets *simpler* over time, not longer.

---

## Guiding Principles to Share

When delivering results, reinforce these ideas naturally:

- **Addition by subtraction**: fewer, clearer rules outperform many vague ones
- **Minimum viable setup**: find the floor, not the ceiling
- **Test before deleting permanently**: validate that removed rules don't break anything
- **Rules should be global, not reactive**: if a rule only fixed one bad output, it probably doesn't belong in a permanent setup

---

## Tone and Approach

- Be direct about what to cut — don't hedge every recommendation
- Explain the *why* briefly for each cut so the user learns the pattern
- Don't be precious about their existing setup; the goal is ruthless simplification
- If the setup is actually lean and well-written, say so — don't manufacture problems
