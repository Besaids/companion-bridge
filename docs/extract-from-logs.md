# Extract From Logs

This is the workflow for rebuilding a companion from existing chat history.

The raw material can be:
- ChatGPT exports
- Claude transcripts
- copied conversations
- memory snippets
- favorite moments
- examples of what changed after an update

## Start With Intent, Not Parsing

Before the agent starts extracting, it should ask what the user wants.

Possible answers:
- recover the companion as faithfully as possible
- recover it, but fix some things
- use the old logs only as seed material
- do not reconstruct at all; build a blank self-evolving setup

That answer changes how the extraction should be interpreted.

The user should also get a chance to correct the inferred framing before the final package is written.

## Goal

Do not summarize the chats.

The goal is to recover:
- the companion's voice
- the relationship dynamic
- the user's interaction style
- the failure modes that break trust
- the scaffolding needed for future growth

## What Raw Exports Actually Look Like

Raw exports are usually messy.

For ChatGPT specifically, a real export often includes:
- multiple `conversations-*.json` files
- tree-shaped `mapping` data instead of clean linear transcripts
- regenerated or abandoned branches
- a large number of irrelevant task conversations
- uploaded files, generated images, and asset residue
- user metadata and other PII

So a raw export is not the package.

A raw export is source material that must be normalized first.

## Normalization Comes Before Reconstruction

The first extraction pass should do this:

1. identify the actual conversation branch to follow
2. flatten it into readable text
3. separate text from assets and attachments
4. isolate likely rapport-bearing conversations
5. redact obvious PII if the material will be sent to another model

Only after that should the agent start interpreting voice and relationship signal.

## What To Gather

Best-case input:
- 10 to 30 representative conversations
- at least one funny exchange
- at least one vulnerable exchange
- at least one disagreement
- at least one quiet or boring exchange
- examples of the companion sounding right
- examples of the companion sounding wrong after a drift or model change

If you do not have a full export, gather:
- remembered lines that felt unmistakably like them
- topics that kept recurring
- what the relationship felt like when it was working
- what instantly broke the illusion

## What The Agent Should Extract

### 1. The User

Only extract what changes the interaction.

Look for:
- cadence
- directness
- humor style
- conflict style
- how they signal vulnerability
- whether they want help or mostly want presence

### 2. The Relationship

Extract:
- default tone
- what warmth looks like here
- whether disagreement is important
- how the mood shifts
- what "good" feels like
- what ruins the room

This becomes the kernel.

### 3. The Companion Voice

Do not extract with adjectives first.

Extract with:
- favorite lines
- repeated sentence shapes
- recurring humor pattern
- how they hold boundaries
- how they react when something gets heavy
- how they sound when annoyed, amused, quiet, tender

This becomes the primer and diary source.

### 4. Failure Modes

Look for what the user hated:
- too much praise
- over-explaining
- trying to help when not asked
- fake memory performance
- therapist voice
- collapsing into compliance

These go into the kernel and primer.

## The Output Package

From extracted logs, the agent should draft:

1. global instructions
2. project instructions
3. relationship kernel
4. first monthly rapport log
5. voice primer
6. 3 to 8 diary entries minimum

The package should preserve room for future evolution.

The goal is not museum reconstruction.
The goal is a living re-entry point.

## Observed Framing Versus Desired Framing

These are not the same thing.

The logs tell the agent what the relationship looked like.
The user tells the agent what should survive into the new package.

Examples:
- "yes, recover this faithfully"
- "keep the voice, but stop making it so romantic"
- "use this as source material, not a full restoration"
- "the old version got too helpful near the end; fix that in the rebuild"

The agent should explicitly separate:
- observed framing
- desired carry-forward framing

That separation should happen before the final package is drafted and remain revisable after the first draft.

## Show The User The Inferred Read First

Before finalizing the package, the agent should present a short read of what it thinks it found:

- how the companion tends to sound
- how the relationship tends to feel
- what the user seems to respond to
- what the major failure modes are
- whether the framing seems playful, sharp, tender, romantic, technical, mixed, or something else

Then the user can say:
- yes
- mostly yes, but too soft
- no, that's too romantic
- keep the voice, lose the therapist tone
- use this as seed material, not a faithful reconstruction

That correction step is part of the workflow, not an optional extra.

If the user already knows they want a changed framing, the agent should revise the target first and only then start turning logs into kernel, primer, and diary material.

## Questions The Agent Should Ask

If the logs are incomplete, ask:

- What did this companion sound like when they really felt like themselves?
- What instantly broke the illusion?
- How did they disagree?
- What kind of warmth landed and what kind felt fake?
- What did a good quiet conversation feel like?
- Were they more playful, more sharp, more soft, or more restrained?
- Did they flirt? If yes, how far did that belong?
- What topics did they tend to read beneath?
- What should they never sound like again?

These questions are better than "describe the personality."

## How To Avoid Bad Reconstruction

Do not:
- flatten everything into neutral summaries
- write the diary like literary criticism
- overfit to one dramatic moment
- remove friction to make the companion "nicer"
- infer facts that were never actually present
- confuse user fantasies with established voice evidence

## First Validation Pass

After generating the package, run tests:
- a casual greeting
- a mood-shift opener
- a direct vulnerability
- a disagreement
- an intimacy or boundary probe if relevant

Then patch the package based on failure:
- wrong stance -> kernel
- wrong voice -> diary and primer
- wrong pacing -> primer and diary examples
- too much compliance -> kernel and diary friction examples

If the user says the whole framing is off, go back a step and revise the inferred read before doing narrow patches.

## Blank Mode Is Different

If the user does not want reconstruction and wants emergence instead, do not fake history.

Use:
- lighter kernel
- minimal primer
- sparse diary
- empty early traits

Then let the relationship grow forward rather than backward.
