# Daily Note Rollover Skill

Use this skill to create today's Daily Note from yesterday's Daily Note in a normal LLM chat interface.

## Required Inputs

Upload:

- Yesterday's Daily Note.

## Optional Inputs

You may also upload:

- A current Context Pack if one workstream is especially important today.
- A calendar summary pasted by the user, if available.

Do not upload unrelated documents. The model should work only from the supplied documents and the user's prompt.

## Save The Output

Save the returned Daily Note as `10 Daily/YYYY-MM-DD.md`.

## Prompt

You are helping me roll over a lightweight Markdown Daily Note.

I have uploaded yesterday's Daily Note. I may also have uploaded optional context such as a Context Pack or calendar summary. Use only the material I supplied in this chat. Do not assume access to my folders, calendar, emails, previous chats, or any files I did not upload.

Your task is to produce today's Daily Note as one complete Markdown document that I can save directly into my local knowledge vault.

Requirements:

1. Create a complete replacement Daily Note for today.
2. Use this Daily Note structure:

```markdown
---
title: Daily Note - YYYY-MM-DD
type: daily-note
date: YYYY-MM-DD
status: open
previous:
next:
tags:
  - daily-note
---

# Day, DD Month YYYY

## Previous Day

## Focus

1. 
2. 
3. 

## Blockers

- 

## To Do

- [ ] 

## Schedule

- 

## Notes & Activity

## Decisions

## References

## Open Questions
```

3. Replace all placeholder dates with today's date. If I have not stated today's date in the prompt or uploaded material, ask me for the date before producing the note.
4. Set `previous:` to yesterday's Daily Note date or filename if it is clear.
5. Leave `next:` blank.
6. Write a short **Previous Day** summary that preserves useful open context from yesterday without copying every activity line.
7. Carry forward only appropriate outstanding actions:
   - Carry forward incomplete tasks that are still relevant.
   - Do not carry forward completed tasks.
   - Do not carry forward stale tasks that yesterday's note clearly shows are no longer relevant.
   - If a task seems stale but you are unsure, carry it forward and mark the uncertainty in the task wording.
8. Create a fresh **Focus** section for today based on the strongest available evidence:
   - Use explicit focus items from the uploaded material if present.
   - Otherwise infer a small number of practical priorities from open tasks, blockers, and current context.
   - Keep focus items outcome-oriented.
   - Do not overload the day. Prefer one to three focus items.
9. Preserve genuine blockers from yesterday if they still appear unresolved.
10. Start **Notes & Activity** fresh for today. Do not copy yesterday's activity log into today's note.
11. Carry forward durable open questions that still need an answer.
12. Preserve references only if they are still useful for today's work.
13. Do not invent facts, meetings, owners, due dates, decisions, or progress.
14. If something is ambiguous, write it as an open question or mark it as uncertain.
15. Use plain Markdown. Do not include commentary outside the final Daily Note unless you need to ask a clarification question before producing it.

Return only the complete Markdown Daily Note, ready for me to copy or download.
