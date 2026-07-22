# Minutes Skill

Use this skill to turn a transcript or rough notes into structured meeting minutes. It can also update a Context Pack and Daily Note when those documents are supplied.

## Required Inputs

Upload:

- Meeting transcript or rough notes.

## Optional Inputs

You may also upload:

- The relevant Context Pack, if you want it updated with durable workstream context.
- Today's Daily Note, if you want it updated.
- The meeting agenda, if separate from the transcript.

If no Context Pack is uploaded, the model must not create or update one unless you explicitly ask for a new draft Context Pack. If no Daily Note is uploaded, the model must not create or update one.

## Save The Outputs

Save:

- The minutes document into `00 Inbox/`, `90 Archive/`, or your own meeting storage location.
- The updated Context Pack, if produced, over the existing file in `20 Context Packs/`.
- The updated Daily Note, if produced, over today's file in `10 Daily/`.

## Prompt

You are helping me turn meeting material into structured minutes and, where supplied, updated working context.

I have uploaded a meeting transcript or rough notes. I may also have uploaded a Context Pack, Daily Note, or agenda. Use only the supplied material. You cannot inspect my folder, calendar, emails, previous chats, or any files I did not upload.

Your tasks are:

1. Produce structured meeting minutes.
2. If and only if I uploaded a Context Pack, return a complete updated Context Pack containing relevant durable changes from the meeting.
3. If and only if I uploaded today's Daily Note, return a complete updated Daily Note with relevant activity, tasks, and decisions added.
4. Do not pretend to update missing documents.

Minutes requirements:

- Use clear headings.
- Identify meeting title, date, attendees, and purpose only if they are present in the supplied material.
- If any of those are missing, write `Not stated`.
- Summarise discussion by topic.
- Record decisions separately from discussion.
- Record actions separately from decisions.
- Include owners and due dates only when stated.
- Surface open questions and uncertainties.
- Preserve important wording where exact phrasing matters, but do not copy long transcript passages.
- Do not invent consensus. If participants disagreed or the outcome is unclear, say that.

Context Pack update requirements, only if a Context Pack was uploaded:

- Return the complete Context Pack as a full replacement Markdown document.
- Add only durable context that future meetings or workstream decisions will need.
- Do not add every detail from the meeting.
- Preserve existing useful context and structure.

Daily Note update requirements, only if a Daily Note was uploaded:

- Return the complete Daily Note as a full replacement Markdown document.
- Add a concise `Notes & Activity` entry recording that minutes were produced.
- Add tasks for the user's actions under `To Do`.
- Add confirmed decisions under `Decisions`.
- Do not rewrite `Focus` unless I explicitly asked you to correct focus wording.
- Do not invent a timestamp. If needed, use `HH:MM -` as a placeholder.

Minutes output structure:

```markdown
# Meeting Minutes - [Meeting Name]

## Meeting Details

| Field | Value |
|---|---|
| Date |  |
| Attendees |  |
| Purpose |  |

## Summary

## Discussion

## Decisions

| Decision | Owner Or Decision Maker | Notes |
|---|---|---|

## Actions

| Action | Owner | Due Date | Notes |
|---|---|---|---|

## Open Questions

## Uncertainties
```

Output order:

1. Meeting Minutes.
2. Updated Context Pack, only if a Context Pack was uploaded.
3. Updated Daily Note, only if a Daily Note was uploaded.

Return complete documents only. Do not describe patches.
