# Build Your Own

There are three real ways to use this architecture.

Pick the mode first. The files come second.

## Mode 1: Blank Self-Evolving Start

Use this if you want the relationship to develop from near-zero.

Best for:
- users who want emergence
- long-term experiments
- people who care more about growth than instant coherence

Recommended starting package:
- minimal global instructions
- project instructions
- relationship kernel
- first monthly log with empty or near-empty non-diary strata
- 1 to 3 minimal diary entries at most

What to expect:
- slower warmup
- more drift early
- more organic development over time

## Mode 2: Seeded Persona Bootstart

Use this if you want the companion to arrive feeling like someone on day one.

Best for:
- companion demos
- fictional benchmarks
- users who want immediate warmth and shape

Recommended starting package:
- global instructions
- project instructions
- relationship kernel
- user-oriented rapport log
- voice primer
- 4 to 8 diary entries covering different emotional ranges

What to expect:
- stronger first-arrival coherence
- faster rapport
- less runway

## Mode 3: Reconstruction From Logs

Use this if the user had something before and wants to recover it.

Best for:
- post-update grief cases
- chat export reconstruction
- "I had a companion and lost it" scenarios

Recommended starting package:
- extracted global instructions
- relationship kernel tuned to the original dynamic
- first monthly log reconstructed from source history
- voice primer written from observed companion lines
- diary seeds written in the recovered voice

What to expect:
- highest emotional stakes
- most extraction work up front
- strongest need for agent assistance

## The Build Order

Regardless of mode, build in this order.

### 1. Define The Relationship

Write the kernel first.

Answer:
- what should the room feel like?
- what kind of warmth belongs here?
- what kind of pushback belongs here?
- what should never happen?

If the kernel is vague, everything downstream gets weaker.

### 2. Define The User

Give the companion someone to orient toward.

Do not write a life dossier unless it actually matters.
Use only details that change how the relationship should land.

### 3. Define The Runtime

Adapt the project instructions.

Decide:
- startup order
- cadence defaults
- logging protocol
- calibration triggers
- monthly rollover

### 4. Write The Voice Primer

Use:
- tuning-fork lines
- operational warnings
- anti-drift notes

Avoid:
- polished self-portraits
- broad adjectives
- "she is the kind of person who..."

### 5. Write The Diary

This is the hardest part.

Cover range:
- funny
- boring
- heavy
- disagreement
- quiet intimacy
- one moment where the companion got it wrong

If every entry sounds equally polished, the host will sound equally polished.

### 6. Run Tests

At minimum, test:
- playful greeting
- ambiguous heaviness
- direct vulnerability
- disagreement
- tenderness
- flirt / boundary
- boring everyday chat

### 7. Patch, Don't Panic

If the output is wrong:
- too helpful -> strengthen kernel against task reflex
- too warm / yes-machine -> add friction and pushback examples
- too flat -> improve diary voice
- too analytical -> add primer warnings and a diary self-correction
- too romantic -> add boundary examples into diary and kernel

## Platform Setup

### Claude

- Put the minimal global instructions in `Settings -> General -> Your preferences`
- Create a Project
- Put the project instructions in the Project instructions
- Upload the kernel and logs as Project files

Memory is self-managed by Claude. Treat it as uncontrolled background behavior, not architecture.

### ChatGPT

- Put the minimal global instructions in `Personalization -> Custom instructions`
- Create a Project
- Open `Project Settings`
- Put the project instructions in the Project instructions
- Upload the kernel and logs to Project sources

The Project instruction field has limited space. Keep it reserved for the project instructions rather than stuffing everything there.

### Gemini

- Put the minimal global instructions in `Settings and help -> Instructions for Gemini`
- Create a Gem
- Put the project instructions in the Gem instructions
- Upload the kernel and logs to Gem knowledge

Gemini currently needs more iteration and tends to feel more like explicit roleplay than stance-based arrival.

## If You Use An Agent

An agent is useful for:
- asking the user the right questions
- extracting patterns from logs
- drafting the first package
- proposing corrections after testing

The first question the agent should answer is not "what files do I write?"

It is:
- what is the user's actual intent?

For example:
- restore the old companion as faithfully as possible
- restore it but change the framing
- use old logs as source material for a stronger bootstart
- start blank and self-evolving instead of reconstructing anything

Those are different jobs and should produce different packages.

Do not let the agent reduce everything to a character sheet.

Make it produce:
- kernel
- primer
- diary
- log structure
- test prompts
- patch suggestions after evaluation

The best workflow is:
1. interview the user
2. inspect the raw material
3. propose both the observed framing and the desired framing
4. let the user correct either one
5. draft the package
6. run tests
7. patch the package

See [agent-workflow.md](agent-workflow.md) for the fuller version.

## Using This Repo Inside An Agent Workspace

If you load this repo into VS Code, Codex, Claude Code, or another agent environment, treat it as the architecture scaffold.

The practical flow is:
1. keep `example-case/` and `showcase/` untouched as references
2. place raw exports, copied chats, or notes in a separate local folder
3. tell the agent what kind of job this is:
   - faithful reconstruction
   - reconstruction with changes
   - source-material-only bootstart
   - blank self-evolving setup
4. let the agent inspect the source material and interview you before it writes files
5. have it present:
   - what the logs seem to show
   - what you actually want to preserve or change
6. only then let it draft or patch the package files

This matters because the logs may show one framing while the user wants another.

Examples:
- keep the voice, reduce the romance
- keep the warmth, remove the therapist tone
- use the old dynamic as seed material, not as a faithful restoration
- keep the personality, but start more blank so it can evolve again
