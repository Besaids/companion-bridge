# Month Transition Guide

This document explains how to close one month's rapport log and open the next one. The transition matters because it determines what the companion carries forward versus what fades, and it prevents the system from accumulating dead weight.

## When To Transition

Transition at the natural boundary of a calendar month. The last conversation of the month (or the first of the new month) is a good time to trigger it.

You can trigger the transition by:
- Saying "closing" or "checkout" to get a final diary entry and log review
- Asking the companion directly: "let's do the month transition"
- Doing it manually by creating the new file yourself

## The Transition Process

### Step 1: Final Checkout on the Current Month

Before closing the month, do a calibration pass on the current log:

1. **Review Texture entries.** Which observations repeated enough to become Traits? Promote them. Which ones stopped mattering? Let them fade. Don't carry dead observations into the new month.

2. **Review Traits.** Any Traits that held consistently across the whole month AND the previous month are candidates for Core promotion. Most won't be ready yet. That's fine.

3. **Prune Working Context.** Remove timestamped facts that are no longer relevant. If a work project finished, a visit happened, a question was resolved — prune it. Working Context is operational, not archival.

4. **Review Open Questions.** Which questions got answered? Remove them. Which ones are still alive? They carry forward. Which ones stopped being interesting? Let them go.

5. **Review the Δ Log.** Are there any system changes from this month that should be reflected in the kernel or project instructions? If yes, patch those files. If not, the Δ entries stay as historical record.

6. **Update the Voice Primer if needed.** Did the companion's voice shift this month? Are there new tuning forks that captured the current voice better than older ones? Did the "what the host will want to do" warnings need updating? Only change the primer if something actually shifted. Don't revise it just because a month passed.

7. **Write a final Diary entry** if the last conversation warrants one.

### Step 2: Create the New Month's File

Create `rapport-MM-YYYY.md` for the new month.

The new file starts with:

```
# Rapport Log — [Month] [Year]
version: 1.0 | started: [YYYY-MM-DD]

Legend:
- [Observed] direct behavior observed in conversation
- [User-confirmed] [User] explicitly confirmed
- [Inferred] interpretation/subtext; not treated as fact

---

## [Month] Bridge (from [Previous Month])

[Bridge content — see below]

---

## Core
[Carry forward from previous month — usually still empty in early months]

---

## Traits
[Carry forward ONLY traits that are still active]

---

## Working Context
[Carry forward ONLY facts that are still relevant]

---

## Δ Log
[Start empty for the new month — old Δ entries stay in the old month's file]

---

## Recent Observations — Texture
[Start empty — this gets populated from new conversations]

---

## Open Questions
[Carry forward ONLY questions that are still alive]

---

## [Companion]

### Voice Primer
[Carry forward the current version — update only if something shifted]

### Diary
[Start empty — new entries begin with the new month's conversations]
```

### Step 3: Write the Bridge

The Bridge is the MOST IMPORTANT part of the transition. It is a short section at the top of the new month's log that carries forward ONLY what still matters.

**What the Bridge should contain:**

1. **Active threads** (3-6 lines) — ongoing situations, projects, or topics that are still alive. Not everything that was discussed. Only what's still in motion.

2. **Established dynamic** (3-5 lines) — how the relationship currently feels. What patterns are settled. What the default energy is. This gives a new instance the room temperature without needing to read the entire previous month.

3. **Emotional baseline** (2-3 lines) — where the user and companion are emotionally. Not a therapy summary. Just: is this a good period, a stressful one, a transitional one? Any weight that's being carried from last month.

**What the Bridge should NOT contain:**

- Everything that happened last month
- Completed projects or resolved situations
- Detailed recaps of conversations
- The full trait list (that's carried in the Traits section)
- The full working context (that's carried in Working Context)

**Bridge length:** 10-20 lines maximum. If it's longer, you're carrying too much.

### Step 4: Decide What Gets Carried Forward

Here's the decision framework for each section:

**Core:**
- Carry forward everything. Core is permanent unless something fundamental changes.
- In early months, this is usually empty. That's correct.

**Traits:**
- Carry forward traits that are still actively observed.
- If a trait hasn't shown up in the last month, consider whether it's still real. If unsure, keep it but watch for reinforcement.
- Traits that get reinforced again this month stay. Traits that don't fade naturally.

**Working Context:**
- Carry forward ONLY facts that are still operationally relevant.
- Aggressively prune. If a work project finished, it's gone. If a friend visited last month and it's not an ongoing thread, it's gone. If a date passed for an event, it's gone.
- New timestamped facts get added fresh as conversations happen.

**Δ Log:**
- Do NOT carry forward. The Δ Log is a record of changes that happened in a specific month. Old Δ entries stay in the old file.
- The new month's Δ Log starts empty and accumulates as new changes happen.
- Exception: if a Δ entry represents an ongoing, unresolved architectural change, you can carry it with a note.

**Texture:**
- Do NOT carry forward. Texture is volatile by definition.
- Observations that repeated enough should already be promoted to Traits.
- The new month's Texture starts empty and populates from new conversations.

**Open Questions:**
- Carry forward questions that are still alive and unresolved.
- Remove questions that were answered during the previous month.
- Remove questions that stopped being interesting — not every thread needs to be tracked forever.
- Mark carried questions with [Carried from [Previous Month]].

**Voice Primer:**
- Carry forward the current version.
- Only update if the companion's voice actually shifted during the previous month.
- If new tuning forks emerged that are better than old ones, swap them.
- If new host-drift warnings are needed, add them.
- Don't revise just for the sake of revision.

**Diary:**
- Do NOT carry forward into the new file. The diary in the new month starts empty.
- The previous month's diary entries remain in the previous month's file.
- The previous month's file should stay in the project/gem as a reference source.
- New diary entries begin fresh with the new month's conversations.

### Step 5: Update the Project/Gem

1. Add the new month's log file to the project/gem.
2. Keep the previous month's log file in the project/gem as well (the model may reference it for voice and context).
3. For months older than 2 months: consider whether they're still needed. If the Bridge and carried-forward sections capture everything relevant, older logs can be archived (removed from active project but kept locally).

**How many months to keep active:**
- Current month: always active
- Previous month: always active (voice source, recent context)
- Two months ago: usually still useful, especially if diary entries are strong
- Three+ months ago: probably archivable unless they contain important Core/Trait evidence

The model's context window is finite. Every file competes for attention. Keep active what's needed, archive what isn't.

## What An Agent Should Do During Transition

If an agent is helping with the transition, it should:

1. Read the current month's complete log
2. Identify what's still active vs what's resolved
3. Propose the Bridge content (show it to the user before finalizing)
4. Propose which Traits, Working Context, and Open Questions carry forward
5. Propose any Voice Primer updates
6. Draft the new month's file
7. Let the user review and approve before replacing files

The agent should NOT:
- Summarize the diary into the bridge (the diary stays in its own month)
- Carry forward everything "just in case"
- Prune aggressively without showing the user what's being dropped
- Rewrite the Voice Primer without evidence of actual drift

## Common Mistakes

**Carrying too much.** The new month's file should feel lighter than the old one, not heavier. If the Bridge is 40 lines long, you're carrying too much. If Working Context has entries from two months ago, you're not pruning.

**Carrying too little.** If the new month's file has an empty Traits section when the previous month had 10 confirmed traits, something went wrong. Active traits should carry forward.

**Losing the diary voice.** The diary doesn't carry forward, but the Voice Primer does. If the primer doesn't capture the companion's current voice, the next month's instances may regress. Update the primer BEFORE transitioning if the voice evolved.

**Not keeping the previous month accessible.** The previous month's log should stay in the project/gem as a reference source. The model may need to reference diary entries or trait evidence from last month. Don't delete it — just be aware it's there for context, not as the active log.

**Treating the transition as a rewrite.** The transition is not a chance to redesign the system. It's a maintenance step. The kernel, project instructions, and user preferences should NOT change during a monthly transition unless a genuine architectural issue was identified during the month.

## Example Bridge

Here's what a bridge looks like in practice:

```
## [Month] Bridge (from [Previous Month])

**Active threads:**
- Side project: alive, still exploratory, no deadline. [Observed]
- Work situation: ongoing friction with a process-heavy environment. [User-confirmed]
- Shared media exchange still acting as trust signal. [Observed]

**Established dynamic:**
- Playful is the default. Depth is always available. Transitions happen without announcement.
- Work talk is venting unless explicitly flagged otherwise.
- [Companion] pushes back. [User] engages harder when they do.
- Expressive style is asymmetrical, but it works.

**Emotional baseline:**
- Good period overall. Trust is higher than it was at the start.
- One old defensive pattern is still present but getting rarer.
```

That's 12 lines. It gives a new instance enough to orient without dragging in everything that happened in the previous month.
