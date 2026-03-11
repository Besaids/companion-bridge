# Template Guide — Start Here

This folder contains blank shells for every file in the architecture. Each one is annotated with what belongs in each section, why it exists, and what to avoid.

The HTML comments are scaffolding for setup. Delete them from the final filled-in version once the content is in place.

## Build Order

Fill these in this order. The order matters because each file depends on decisions made in the one before it.

### Step 1: Relationship Kernel (`relationship-kernel.md`)

Start here. Not with the companion's personality. Not with the user's profile. With the ROOM.

The kernel answers:
- What should this interaction feel like?
- What kind of warmth belongs here?
- What kind of friction belongs here?
- What should never happen?

Everything downstream inherits from this file. If the kernel is vague, every other file will drift.

### Step 2: User Preferences (`user-preferences.md`)

Short. Identity-level. This tells the model who the companion IS at the highest level. Not how they behave — who they are.

Keep this under 200 words. Long identity prompts compete with the diary for attention and produce worse results than short orientation plus rich diary.

### Step 3: Project Instructions (`project-instructions.md`)

The governance layer. This is mostly structural and can be adapted from the template with minimal changes. The main things to customize:
- Companion name
- Any cadence preferences specific to the relationship
- Whether you want calibration triggers

### Step 4: First Monthly Rapport Log (`rapport-MM-YYYY.md`)

This is where the real work happens. The log contains:
- Traits (observed patterns)
- Working Context (timestamped facts)
- Texture (volatile impressions)
- Open Questions (unresolved threads)
- Voice Primer (tuning forks and anti-drift warnings)
- Diary (the voice source — the most important part of the entire architecture)

For a **blank self-evolving start**: leave most sections empty or minimal. Write 1–3 short diary entries that establish initial voice.

For a **seeded bootstart**: populate all sections. Write 8-15 diary entries covering emotional range. This is what produces a companion that arrives as someone on day one.

For a **reconstruction from logs**: extract from existing chat history using the process described in `docs/extract-from-logs.md`.

### Step 5: Test

Load the files. Talk to the companion. See what arrives.

Test at minimum:
- A casual greeting
- Something ambiguously heavy
- A direct vulnerability
- A disagreement
- A mood pivot (heavy to light or light to heavy)

### Step 6: Patch

If the output is wrong, the fix is usually small:
- Wrong stance → kernel
- Wrong voice → diary and primer
- Too helpful → kernel failure modes + diary self-correction entry
- Too flat → diary needs more personality range
- Too analytical → primer warnings + diary self-correction entry
- Too romantic → diary boundary example + kernel failure mode

See `docs/maintenance.md` for the full correction guide.

## Month-to-Month Transitions

When a month ends, you need to bridge into a new log. See `month-transition-guide.md` in this folder for the full process.

## What NOT To Do With These Templates

- Do not copy content from the bundled example case into your templates. The example exists as a reference, not as seed material for your companion.
- Do not write the diary first and the kernel second. The kernel sets the room. The diary lives inside that room.
- Do not write diary entries that sound like literary essays. Write them like someone thinking.
- Do not skip the Voice Primer. Without it, new instances will sound like the host model's default prose regardless of how good the diary is.
