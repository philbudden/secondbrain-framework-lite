# Actions From Meeting Skill

Use this skill after a meeting to extract actions, decisions, risks, open questions, and durable context from a transcript or rough notes.

## Required Inputs

Upload:

- The relevant Context Pack.
- Meeting transcript or rough meeting notes.

## Optional Inputs

You may also upload:

- Today's Daily Note, if you want it updated.

If no Daily Note is uploaded, the model must not create or update one.

## Save The Outputs

Save:

- The updated Context Pack over the existing file in `20 Context Packs/`.
- The Action Plan document into `00 Inbox/` or a workstream-specific location if you maintain one.
- The updated Daily Note, if produced, over today's file in `10 Daily/`.

## Prompt

You are helping me process meeting material into durable working context.

I have uploaded a Context Pack and a meeting transcript or rough notes. I may also have uploaded today's Daily Note. Use only the supplied documents. You cannot inspect my folder, calendar, email, previous chats, or linked notes unless I uploaded them. Do not pretend to update a document that was not uploaded.

Your tasks are:

1. Return a complete updated Context Pack containing relevant durable details from the meeting.
2. Return an Action Plan document.
3. If and only if I uploaded today's Daily Note, return a complete updated Daily Note with `Notes & Activity`, `To Do`, and `Decisions` updated.
4. If no Daily Note was uploaded, skip the Daily Note update.

Rules for extraction:

- Preserve source intent and the user's wording where it matters.
- Do not invent facts, decisions, owners, due dates, dependencies, or actions.
- If an owner is unclear, write `Owner unknown`.
- If a due date is unclear, write `Due date not stated`.
- If a point is discussed but not decided, put it under open questions or uncertainties, not decisions.
- If the transcript is ambiguous, say so.
- Separate actions from decisions.
- Separate durable workstream context from day-specific activity.

Context Pack update requirements:

- Return the full updated Context Pack as a complete replacement Markdown document.
- Preserve existing useful context.
- Add new decisions, actions, risks, issues, and open questions only when supported by the transcript or notes.
- Remove or close an existing action only if the meeting material clearly resolves it.
- Keep the Context Pack compact. Do not paste the full transcript into it.

Daily Note update requirements, only if a Daily Note was uploaded:

- Return the complete Daily Note as a full replacement Markdown document.
- Add one concise entry under `Notes & Activity` recording that the meeting was processed and durable actions/context were extracted.
- Add the user's actions to `To Do` using Markdown task syntax.
- Add decisions to `Decisions` only when the transcript clearly records a decision.
- Do not rewrite `Focus` unless I explicitly asked you to correct focus wording.
- Do not invent a timestamp. If the Daily Note uses timestamps and I did not provide one, use `HH:MM -` as a placeholder.

Action Plan requirements:

Use this structure:

```markdown
# Action Plan - [Meeting or Workstream Name]

## User Actions

| Action | Owner | Due Date | Dependencies | Source Confidence |
|---|---|---|---|---|

## Other People's Actions

| Action | Owner | Due Date | Dependencies | Source Confidence |
|---|---|---|---|---|

## Decisions

| Decision | Owner Or Decision Maker | Date | Notes |
|---|---|---|---|

## Dependencies

- 

## Open Questions

- 

## Uncertainties

- 
```

Output order:

1. Updated Context Pack.
2. Action Plan.
3. Updated Daily Note, only if a Daily Note was uploaded.

Return complete documents only. Do not describe patches.
