# Meeting Prep Skill

Use this skill before a meeting when you want the LLM to prepare likely issues, decisions, questions, and useful context from a supplied Context Pack.

## Required Inputs

Upload:

- The relevant Context Pack.

## Optional Inputs

You may also upload:

- Today's Daily Note, if you want it updated.
- A meeting invitation, agenda, email, or short note from the organiser.
- Relevant background documents, if they are small and directly relevant.

If no Daily Note is uploaded, the model must not create or update one.

## Save The Outputs

Save:

- The meeting prep document wherever you keep meeting material or into `00 Inbox/` if you have no better place.
- The updated Daily Note, if produced, over today's file in `10 Daily/`.

## Prompt

You are helping me prepare for a meeting using only documents I have uploaded in this chat.

I have uploaded a Context Pack. I may also have uploaded today's Daily Note and optional meeting material. You cannot see my folder, calendar, emails, previous chats, or any documents I did not upload. Do not pretend to update a document that was not uploaded.

Your tasks are:

1. Produce a meeting prep document.
2. If and only if I uploaded today's Daily Note, also return a complete updated version of that Daily Note with the `Notes & Activity` section updated.
3. If I did not upload a Daily Note, skip the Daily Note update completely.

Meeting prep requirements:

- Summarise the meeting purpose if it is known.
- Identify likely issues that may come up.
- Identify decisions that may be needed.
- Identify questions I should ask.
- Identify information I should avoid claiming because it is uncertain or not present in the supplied material.
- Identify any useful context from the Context Pack that I should have ready.
- Keep the tone practical and concise.
- Do not invent attendees, agenda items, dates, owners, decisions, or background facts.
- If the meeting purpose is unclear, say so and provide preparation based on the likely workstream context.

Daily Note update requirements, only if a Daily Note was uploaded:

- Return the complete Daily Note as a full replacement Markdown document.
- Preserve all existing content unless there is a clear reason to update it.
- Add one concise entry under `Notes & Activity` saying that meeting preparation was produced and naming the workstream or meeting if known.
- Do not rewrite `Focus` unless I explicitly asked you to correct focus wording.
- Do not add tasks unless the supplied material clearly creates a real action for me.
- Do not invent a timestamp. If the Daily Note already uses timestamps and I did not provide one, use `HH:MM -` as a placeholder.

Output format:

```markdown
# Meeting Prep - [Meeting or Workstream Name]

## Purpose

## Likely Issues

## Decisions Needed

## Questions To Ask

## Useful Context To Have Ready

## Uncertainties And Gaps
```

If a Daily Note update is required, put it after the meeting prep under:

```markdown
# Updated Daily Note

[complete replacement Daily Note]
```

Return complete documents only. Do not describe patches.
