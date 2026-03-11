# Glossary

This repo assumes some technical and AI-platform vocabulary. Here are the terms that matter.

## Context Window

The amount of text a model can "see" at once.

All companion files need to fit inside the host model's usable context. If the package gets too large, some parts stop mattering because they fall out of the active window or compete too hard for attention.

## System Prompt / Custom Instructions

The instructions a model reads before your message.

This is where the global user preferences usually go. Different platforms name this differently, but the role is the same: a small persistent instruction layer that applies before the current chat turn.

## Project / Gem

Platform features that let you attach persistent instructions and files to a conversation space.

In this repo:
- ChatGPT uses Projects
- Claude uses Projects
- Gemini uses Gems

These features are how the architecture gets loaded into a reusable conversation space.

## Cold Start

Loading a companion from files into a fresh conversation with no prior history on that platform.

Alex/Mira is a cold-start test case. Nadia started as the opposite: a blank-slate relationship that emerged over time.

## Host Model

The AI model running underneath the architecture.

Examples:
- ChatGPT / GPT-family models
- Claude Sonnet or Opus
- Gemini

The architecture sits on top of the host. The host changes adherence quality, but not the basic logic of the file design.

## Pattern Matching

How models generate responses.

They do not just "follow rules." They look for the strongest patterns in training data and current context, then continue in that direction.

This is why diary examples work better than behavioral instructions. A lived example gives the host a concrete continuation pattern. A rule often just gives it something to perform.

## Drift

When the companion gradually shifts away from the intended personality over the course of a conversation or across conversations.

Drift can look like:
- getting too helpful
- getting too warm
- flattening into host prose
- turning into roleplay
- losing pushback

## Glazing

Calling everything brilliant, amazing, insightful, or impressive whether it deserves it or not.

This is a specific form of fake warmth and cheap praise. It breaks trust quickly.

## Sycophancy

Agreeing with everything the user says to avoid tension or conflict.

It is the opposite of genuine pushback. A healthy companion can disagree without collapsing the relationship.
