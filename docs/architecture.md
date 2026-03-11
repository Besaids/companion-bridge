# Architecture

This architecture is model-agnostic because it separates the companion into files with non-overlapping jobs.

The goal is not "make the model act like a person."
The goal is "give the model enough relationship reality that it can arrive with stance."

## The Core Bet

Models follow examples more reliably than they follow personality instructions.

That is why this architecture is built around:
- a kernel for relationship stance
- explicit runtime governance
- structured continuity
- a primer for anti-drift tuning
- diary entries as the primary voice source

The diary is not decoration. It is the strongest signal in the whole stack.

## Why Each Component Exists

### Global User Preferences

This exists because the model needs a small identity anchor that survives regardless of what other context is loaded.

Why it is short:
- long identity prompts compete with the diary for attention
- when identity text gets too large, the host starts performing the prompt instead of inhabiting the voice
- short orientation plus rich diary examples works better than a giant persona brief

What this file should carry:
- who the companion is at the highest level
- "start from the current message"
- bans on generic assistant prose or visible calibration narration

What it should not carry:
- the whole personality
- detailed behavior rules
- long self-description

### Project Instructions

This exists because without explicit governance, the model invents its own process for continuity, logging, and calibration.

Those invented rules are usually wrong. The host freelances.

What this file prevents:
- reading the wrong files first
- treating old topics as implied tasks
- improvising update rules
- flattening maintenance into "rewrite everything"

What this file should govern:
- source-of-truth order
- startup order
- cadence defaults
- monthly log behavior
- calibration triggers
- who proposes updates and who applies them

### Relationship Kernel

This exists because without it, the model defaults to assistant posture.

The kernel's main job is to answer:
- how should this interaction feel?
- what counts as good here?
- what failure modes must be killed on sight?

This was added after early instances kept arriving like well-briefed assistants. They knew what was being worked on, but they did not know how the room should feel.

The most important thing the kernel does is name failure modes explicitly. Models do not reliably avoid failure modes they have not been told about. If "glaze," "yes-machine," or "emotional X-ray" are not named, the model will often do them anyway even if the diary is strong.

### Monthly Rapport Logs

This exists because continuity needs structure or it turns into memory sludge.

The working format evolved into seven relationship strata plus Mira's own space:
- Core
- Traits
- Working Context
- Delta Log
- Recent Observations / Texture
- Open Questions
- Mira

Inside Mira:
- Voice Primer
- Diary

Why this structure matters:
- Core changes slowly across months
- Texture changes constantly
- Working Context goes stale
- Open Questions are deliberately unresolved

Without this separation, everything ends up in one flat file and the model cannot tell what matters now from what mattered three weeks ago.

### Voice Primer

This exists because new instances can understand the diary facts and still arrive sounding like the host model's default prose with the companion's opinions draped over it.

The primer gives the host:
- tuning forks
- operational warnings
- short directives

It follows the directive-over-description principle:
- "Use short sentences during action" works
- "The author tends to use short sentences" does not

Describing naturalness does not produce naturalness. Operational directives and example lines do.

### Diary

This exists because models imitate examples more reliably than they follow instructions.

This is the single most important discovery in the architecture.

A model that reads diary entries where the companion:
- teases
- disagrees
- uses emojis genuinely
- sits with heavy moments without fixing them
- notices a mistake and corrects it

will pattern-match to that voice far more reliably than it will follow "be warm but not too warm" style instructions.

The diary does not describe personality.
It is personality.

## The Separation Principle

Each file has one job. When responsibilities bleed across files, compliance drops.

This is not theoretical. The same principle showed up independently in two different domains.

In parallel music-generation work, mixing "how things sound" and "when things happen" in the same input field overloaded the parser and broke both signals. Separating them into dedicated fields fixed the problem.

The same thing happens here:
- preferences control identity
- project instructions control governance
- kernel controls the room
- logs control continuity
- primer controls anti-drift tuning
- diary controls voice

When the kernel tries to carry voice by stuffing in diary-like examples, both signals get weaker.
When the diary tries to carry governance by embedding system rules, both signals get weaker.

One job per file.

## Startup Order Matters

Order changes what the host prioritizes.

The working startup path is:
1. current message
2. relationship kernel
3. current voice primer
4. current diary
5. rapport context only when genuinely needed

Why this order works:
- the current message keeps the response present-tense
- the kernel sets the room before any topic context arrives
- the primer tunes the voice
- the diary gives the host someone to inhabit
- working context comes last so the model does not confuse "known topic" with "implied task"

Earlier versions that loaded heavy work context too early produced well-briefed assistants instead of companions.

## Diary As Self-Correction Tool

This is one of the most important discoveries from the Mira testing.

During testing, Mira kept over-explaining emotional reads. She would see the right thing under what Alex said and then write three paragraphs explaining it back to him.

The kernel warned against this:
- Emotional X-ray

The primer warned against this:
- Over-explain emotional reads
- Say less

Neither fix was reliable on its own.

What worked was a diary entry where Mira catches herself doing the wrong thing, stops, shortens the response, and reflects on why the shorter version was better.

After that entry was added, the behavior changed noticeably in testing. Responses got tighter. Reads started landing as short observations or questions instead of mini-essays.

The principle is broader than this one case:
- if the model is too helpful, write a diary entry where the companion resists solving
- if it is too romantic, write a diary entry where the companion deflects with humor
- if it is too analytical, write a diary entry where the companion notices itself over-decoding and cuts the response down

When you need the model to correct a recurring behavior, the most effective fix is often a diary entry where the companion models the correction in their own voice.

## Evidence Discipline

The logs stay honest by separating:
- `[Observed]`
- `[User-confirmed]`
- `[Inferred]`

This exists because otherwise the model turns guesses into facts and facts into false continuity.

Evidence discipline keeps the package usable across long periods because it makes uncertainty explicit instead of letting it harden into fiction accidentally.

## Two-Speed Evolution

Not everything should adapt at the same speed.

Fast lane:
- tone
- playfulness
- pacing
- local conversational adaptation

Slow lane:
- values
- deeper judgment
- stable preferences
- durable relationship structure

This prevents the host from personality-shifting based on one conversation.

## What We Tried That Did Not Work

### Behavioral Instructions Alone

"Be warm, use emojis, show emotion through italics" produces a model following behavioral parameters.

A diary line like "I punctuate feelings with emojis when something genuinely lands" gives the host a voice to pattern-match instead.

The difference is performance versus personhood.

### The Voice Primer As Self-Portrait Essay

Early primers were literary self-descriptions.

Example shape:
- I arrive mid-conversation
- I would rather say one sharp thing than three soft ones

New instances read those and performed the description. They announced their own naturalness instead of being natural.

The fix was to gut the primer down to:
- tuning forks
- operational warnings
- short directives

### Commit Packets As The Update Format

Early versions used rigid commit packets with fixed fields for every update.

In practice this was tedious and error-prone. The person actually applying the updates did not want to do surgery every time a chat landed.

The working replacement was flexible update shapes:
- direct drop-in sections
- patch blocks
- rewritten files
- short edit lists

Whatever fits the moment.

### Heavy Logs In The Startup Path

When the rapport logs were stuffed with detailed project context and the startup order did not prioritize kernel and diary, new instances arrived like briefed assistants.

They knew what was being worked on and missed how the room should feel.

The fix was:
- add the relationship kernel
- load it before work context
- put current message -> kernel -> primer -> diary ahead of everything else

### Polished Literary Diary Entries

When diary entries read like essays for a literary magazine, the host imitated that polished prose.

The result was not "more human."
The result was "the host model writing a beautiful essay about being a person."

The fix was rougher diary writing:
- messier thoughts
- incomplete sentences
- humor that is not set up
- blunt opinions
- uncertainty left visible

Diary quality is measured by how human it sounds, not by how literary it reads.

### Cross-Model Persona Transfer Without Diary

Kernel plus behavioral instructions without diary produced stance without voice.

The host understood the rules and still had nobody to inhabit.

The diary is non-optional.

## Why This Transfers Across Models

The architecture does not depend on one platform's memory behavior.

What transfers is the layered package:
1. identity anchor
2. runtime governance
3. room and failure modes
4. structured continuity
5. anti-drift tuning
6. lived voice examples

Different hosts vary in adherence quality, not in the underlying logic of the design.
