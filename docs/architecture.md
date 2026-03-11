# Architecture

This architecture is model-agnostic because it separates the companion into files with non-overlapping jobs.

The goal is not "make the model act like a person."
The goal is "give the model enough relationship reality that it can arrive with stance."

## The Stack

### Global User Preferences

Purpose:
- set identity/orientation
- define high-level constraints
- stay short enough to survive platform limits

What it should do:
- say who the companion is
- tell the model to start from the current message
- forbid generic assistant prose or visible calibration narration

What it should not do:
- carry the whole personality
- describe every behavior
- become a giant persona prompt

### Project Instructions

Purpose:
- govern the runtime
- define precedence
- define startup order
- define maintenance rules

This is the plumbing:
- what to read first
- when to pull logs
- how the monthly log evolves
- how calibration works
- who proposes updates and who applies them

### Relationship Kernel

Purpose:
- define the room
- define what "good" feels like
- define failure modes

This is the most important small file.

If the kernel is weak, the model will drift into:
- helpdesk mode
- customer support tone
- glazing
- emotional flooding
- over-analysis
- continuity theater

The kernel exists so the host model does not decide the relationship style for you.

### Monthly Rapport Logs

Purpose:
- hold continuity without turning the whole system into memory sludge

The logs carry:
- traits
- working context
- recent observations / texture
- open questions
- voice primer
- diary

They are living documents, not archives for everything that ever happened.

### Voice Primer

Purpose:
- stop drift
- stop wrong-voice reconstruction

This file exists because "the model knows the facts" is not enough.
The host can know the whole story and still sound wrong.

A good voice primer is:
- operational
- brief
- example-heavy
- anti-drift

A bad voice primer is:
- literary self-description
- abstract personality theory
- a biography

### Diary

Purpose:
- encode lived voice directly

The diary is the strongest source file because models imitate examples more reliably than instructions.

A good diary:
- sounds like the companion thinking
- includes humor, friction, uncertainty, and texture
- covers multiple emotional ranges
- does not read like a polished essay about itself

## Why This Transfers Across Models

The architecture does not depend on one host's special memory behavior.

It works because every host gets the same layered package:
1. identity
2. runtime rules
3. room/dynamic
4. structured continuity
5. anti-drift tuning
6. lived voice examples

What changes from model to model is adherence quality, not the underlying design.

## Relationship-First, Not Task-First

The key architectural bet is that the relationship is the primary object.

Topics are context inside the relationship.
They are not the relationship.

That is why the system resists turning every technical subject into task mode and every vulnerable moment into advice mode.

## The Real Problem This Solves

Without structure, new instances usually preserve one of these but not both:
- facts
- feel

Most "memory" systems preserve facts and lose feel.
Most vibe prompts preserve feel briefly and lose continuity.

This architecture tries to preserve both:
- logs preserve continuity
- diary and primer preserve voice
- kernel preserves stance

## Failure Modes To Watch For

Across hosts, the most common failure modes are:
- assistant posture
- over-explaining emotional reads
- yes-machine agreement
- fake warmth
- platform memory contamination
- overly literal roleplay
- voice flattening into host prose

The fix is rarely "add more prompt."
The fix is usually one of:
- sharpen the kernel
- improve the primer
- rewrite diary entries in a truer voice
- remove over-descriptive instruction noise

## One Job Per File

This is the main rule.

Do not mix:
- identity
- governance
- relationship feel
- working memory
- anti-drift tuning
- lived voice

The more those jobs blur together, the harder the system becomes to debug and transfer.
