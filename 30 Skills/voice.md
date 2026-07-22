# Voice Skill

Use this skill to analyse approved writing samples and produce a practical voice guide that can help future drafting.

This is adapted from the full SecondBrain `voice` skill, but rewritten for chat-only use. It cannot inspect folders or know which documents are approved unless you upload them and label them.

## Required Inputs

Upload:

- At least two approved writing samples, if available.

If you have only one sample, the model may produce a provisional guide but must say the evidence is narrow.

## Optional Inputs

You may also upload:

- An existing voice guide to update.
- A note containing declared style preferences.
- A draft you want checked against the voice guide. If you upload a draft, make clear that it is not evidence for learning your voice unless you explicitly say otherwise.

## Save The Output

Save the returned voice guide somewhere stable, such as `20 Context Packs/voice-guide.md` or another location you use for reference material.

## Prompt

You are helping me create or update a practical writing voice guide from approved writing samples.

Use only the documents I uploaded and the instructions in this prompt. You cannot inspect my folders, previous chats, published work, or drafts unless I upload them. Do not infer my voice from this chat unless I explicitly say to treat it as evidence.

Important evidence rules:

- Treat only documents I label as approved, published, final, or representative as voice evidence.
- If I upload drafts, rough notes, meeting notes, or context packs, do not use them as voice evidence unless I explicitly instruct you to.
- If I upload an existing voice guide, preserve any declared preferences unless I explicitly ask you to change them.
- Do not infer a confident style rule from one example.
- Separate stable habits from topic-specific or format-specific choices.
- Use short examples only when they add precision.
- Do not flatter. Be concrete and useful.

Analyse:

- tone and stance;
- sentence rhythm;
- paragraph shape;
- vocabulary and diction;
- openings and closings;
- transitions;
- argument structure;
- formatting habits;
- rhetorical habits;
- things to avoid;
- differences between formats if the samples vary.

Output a complete voice guide in this structure:

```markdown
# Voice Guide

## Status

State whether this guide is provisional, developing, or well-supported, and why.

## Evidence Used

List the uploaded documents used as voice evidence. If any uploaded document was excluded, say why.

## Declared Preferences

Preserve existing declared preferences if supplied. Otherwise leave this section blank or state that none were supplied.

## Core Voice

## Tone And Stance

## Structure And Argument

## Sentence And Paragraph Rhythm

## Diction

## Openings

## Closings

## Formatting

## Characteristic Moves

## Avoid

## How To Use This Guide When Drafting

## Confidence And Gaps
```

If I uploaded an existing voice guide, return a complete replacement guide rather than a list of edits.
