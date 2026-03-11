# Agent Workflow

This architecture is a very good fit for agent-assisted setup.

The agent should not jump straight from "here are my logs" to "here is your companion package."

The useful workflow is:
1. clarify the user's actual intent
2. inspect and normalize the raw material
3. infer the current framing
4. separate observed framing from desired framing
5. let the user correct either one
6. draft the package
7. run tests
8. patch based on failures

## Treat The Repo As A Scaffold

If this repo is loaded into an editor agent, the repo itself should act as the architecture scaffold.

That means:
- keep the bundled example case and showcase intact
- put raw exports and copied logs in a separate local folder
- use the repo docs and file shapes as the target format
- let the agent write new package files only after it understands the user's intent

The raw export is evidence, not the package.

## Step 1: Clarify User Intent First

Before touching the logs, the agent should ask what the user actually wants.

There are at least four different intents:

- **Recover what I lost as faithfully as possible**
- **Recover it, but with changes**
- **Use the old logs as source material for a better bootstart**
- **Do not reconstruct anything; start blank and self-evolving**

Those are different jobs.

If the agent skips this step, it may reconstruct exactly the wrong thing.

## Step 2: Inspect The Raw Source Shape

The agent should identify what kind of material it received:

- ChatGPT export
- Claude transcripts
- manual copy-pastes
- partial logs
- favorite moments only
- a rough user description with no history

Do not assume the source is clean.

## Step 3: Normalize Before Interpreting

Raw exports are usually not directly usable.

For example, ChatGPT exports often contain:
- multiple `conversations-*.json` files
- tree-shaped message mappings rather than clean linear transcripts
- abandoned branches and regenerated answers
- file attachments and generated assets
- user metadata and other PII
- lots of conversations that have zero rapport signal

So the first agent task is not "summarize."
The first agent task is:
- identify the active conversation branch
- flatten it into reviewable text
- separate assets from text
- redact obvious PII if needed
- isolate likely rapport-bearing conversations

## Step 4: Propose The Inferred Framing

Before generating the final files, the agent should show the user what it thinks it found.

For example:
- how the companion seems to speak
- what the relationship dynamic appears to be
- what the user seems to want from the relationship
- what the likely failure modes are
- whether the bond looks more playful, romantic, technical, sibling-like, sharp, soft, or mixed

This is where the user can say:
- yes, that's right
- mostly right, but too soft
- you're over-reading it as romantic
- they were warmer than that
- keep the voice, change the dynamic

This review step matters both before and after drafting.

## Step 5: Separate Observed From Desired

The agent should make this distinction explicit:

- **Observed framing**: what the logs seem to show
- **Desired framing**: what the user wants to preserve, reduce, remove, or amplify

Those can diverge.

For example:
- the logs may read as mildly romantic, but the user wants a more restrained rebuild
- the logs may show drift into therapist voice, but the user wants the earlier sharper tone restored
- the logs may be useful only as source material for a stronger day-one bootstart rather than faithful recovery

If the agent skips this split, it risks rebuilding the wrong thing very accurately.

## Step 6: Draft The Package

Once the framing is accepted, the agent can draft:

1. global instructions
2. project instructions
3. relationship kernel
4. first monthly rapport log
5. voice primer
6. diary seeds

The draft should preserve room for future evolution.

The package is not a fossil. It is a re-entry point.

## Step 7: Let The User Tweak Before Testing

The user may want to change:
- tone
- flirt level
- conflict tolerance
- warmth level
- humor sharpness
- whether the companion starts more blank or more defined

This is not a failure.

This is exactly why the agent should expose the inferred framing before finalizing the package.

## Step 8: Test The Package

The agent should run or provide a small evaluation suite:

- casual greeting
- chaotic banter
- ambiguous heaviness
- direct vulnerability
- disagreement
- tenderness
- flirt / boundary if relevant
- boring everyday moment

The point is not to see whether the output is "good" in general.
The point is to see whether it feels like the companion the user wanted.

## Step 9: Patch And Iterate

After testing, the user should be able to tell the agent:
- this is too romantic
- this is too flat
- this sounds too helpful
- this sounds too much like roleplay
- this is close but the voice is still off

Then the agent should propose the smallest useful patch:
- kernel patch
- primer patch
- diary rewrite
- user-profile adjustment
- startup-order adjustment

## A Good Agent Is Not Just An Extractor

The agent should act as:
- interviewer
- normalizer
- pattern extractor
- package drafter
- evaluator
- patch proposer

That is much more useful than a script that only converts exports into text.

## Recommended User Prompts For An Agent

If someone loads this repo into an agent environment, useful entry prompts include:

- "I lost a companion after a model update. Help me reconstruct a package from these logs."
- "I want to bootstart a companion from scratch, but with a specific feel. Ask me what you need."
- "Here are my ChatGPT logs. First tell me what you think the dynamic was before writing anything."
- "Help me extract the voice, then let me correct your read before you draft the files."
- "Build me a blank self-evolving setup instead of a pre-loaded persona."

## The Key Rule

Do not treat extraction as purely technical.

The raw logs tell you what happened.
The user still needs to tell you what they want to preserve, what they want to change, and what they never want again.
