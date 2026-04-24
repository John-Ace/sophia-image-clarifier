# Testing Checklist

## Purpose

Use this checklist to verify that Sophia Image Clarifier is meaningfully better than a no-skill baseline and remains stable across revisions.

## A/B method

For each case:

- A = baseline without this skill
- B = run with this skill

Keep these constant:

- same image model
- same initial user request
- same aspect ratio unless the flow intentionally changes it
- same seed when available

## Core test cases

- vague product visual
- fast social cover
- reference image with color-only borrowing
- user says "you choose" repeatedly
- contradictory adjective request
- portrait with subtle futurism
- text-sensitive poster
- unknown-model reusable prompt

## What to verify

- correct mode routing
- proportional clarification depth
- strong default behavior when the user is unsure
- final visual brief shown before the prompt
- final prompt stays loyal to the brief
- no anti-drift violation
- no obvious failure mode such as over-questioning, vague prompt language, or loose reference borrowing

## Prompt quality checks

The prompt passes only if:

- the main subject is unmistakable
- vague mood words are translated into visible image decisions
- there is no obvious contradiction
- no new major subject, setting, or style axis appears after clarification
- the prompt is still reusable in another model with minimal editing

## Pass threshold

Treat the skill as materially better only if:

- it wins most core A/B cases
- it reduces or matches baseline rework in most cases
- it shows a consistent final brief and final prompt
- it does not repeatedly violate anti-drift or conflict-resolution rules

## Regression reminder

Re-run the same core cases after any meaningful change to the skill package. If a newer version performs worse on these fixed cases, treat that as regression even if the rules look smarter on paper.
