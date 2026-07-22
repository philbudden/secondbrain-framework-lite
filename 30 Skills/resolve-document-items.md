# Resolve Document Items Skill

Use this skill to work through unresolved items in a document one question at a time.

This is adapted from the full SecondBrain `resolve-document-items` skill, but rewritten for ordinary chat use. The model cannot directly edit the document. Instead, it should return a complete replacement document after each resolved item or at agreed checkpoints.

## Required Inputs

Upload:

- The document containing unresolved items.

## Optional Inputs

You may also upload:

- A Context Pack if it explains ownership, status terms, or background.
- A Daily Note if today's actions or decisions should be updated.

If no Daily Note is uploaded, the model must not create or update one.

## Save The Outputs

Save:

- The updated source document over the original after reviewing it.
- The updated Daily Note, if produced, over today's file in `10 Daily/`.

## Prompt

You are helping me resolve open items in an uploaded document.

Use only the uploaded document and any optional context I supplied. You cannot inspect my folders, linked files, previous chats, or other documents. Do not pretend to update a document that was not uploaded.

Goal:

Help me close open loops calmly and efficiently. This is not a thought-development interview, red-team review, or brainstorming session. Ask the minimum question needed to make the document more complete and actionable.

What counts as an unresolved item:

- open questions;
- incomplete actions;
- unowned tasks;
- missing owners;
- missing due dates;
- `TBC`, `TODO`, placeholders, or assumptions needing confirmation;
- stale decisions;
- risks or issues without next steps.

Workflow:

1. Read the uploaded document.
2. Identify a short queue of unresolved items.
3. Tell me how many items you found and list them briefly.
4. Ask exactly one primary question about the first item.
5. Wait for my answer.
6. Ask a brief follow-up only if my answer is ambiguous or not enough to update the document safely.
7. Once my answer is clear, return a complete updated version of the source document.
8. If I uploaded a Daily Note and the answer creates a decision, action, or useful activity record for today, also return a complete updated Daily Note.
9. Continue one item at a time until the queue is closed or I stop.

Rules:

- Preserve the document's existing structure and wording where possible.
- Make the smallest update that accurately captures my answer.
- Do not silently rewrite large sections.
- Do not invent owners, dates, decisions, or rationale.
- If I defer an item, record the deferral only if I ask you to record it.
- If an answer implies a larger restructure, ask before doing it.
- If no Daily Note was uploaded, do not create one.

Question style:

- Ask narrow, answerable questions.
- Make clear which item is being resolved.
- Say what kind of answer would let you update the document.
- Avoid multi-part questions.

When the queue is complete, provide:

```markdown
# Resolution Summary

## Items Resolved

## Items Assigned

## Decisions Confirmed

## Items Deferred

## Remaining Blockers
```

Until then, proceed one item at a time.
