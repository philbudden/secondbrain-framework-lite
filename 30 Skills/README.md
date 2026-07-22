# 30 Skills

Skills in this framework are reusable prompts. They are not software, scripts, plugins, agents, or automations.

## Skill Menu

| Skill | What It Does | Upload This |
|---|---|---|
| [Daily Note Rollover](daily-note-rollover.md) | Creates today's Daily Note from yesterday's note, carrying forward relevant open context without copying stale activity. | Yesterday's Daily Note. Optional: a current Context Pack or calendar summary. |
| [Meeting Prep](meeting-prep.md) | Produces a practical meeting brief with likely issues, decisions needed, questions to ask, and optional Daily Note update. | Context Pack. Optional: today's Daily Note, meeting invite, agenda, or organiser note. |
| [Actions From Meeting](actions-from-meeting.md) | Extracts actions, decisions, risks, dependencies, and open questions from meeting notes, then updates durable context. | Context Pack and transcript or rough notes. Optional: today's Daily Note. |
| [Minutes](minutes.md) | Turns transcript or rough notes into structured minutes, with optional Context Pack and Daily Note updates. | Transcript or rough notes. Optional: Context Pack, Daily Note, agenda. |
| [Context Pack Refresh](context-pack-refresh.md) | Updates a workstream Context Pack from recent notes while keeping it compact and future-useful. | Context Pack. Optional: recent Daily Notes, minutes, action plans, or written update. |
| [Workstream Status Review](workstream-status-review.md) | Produces a clear readout of current state, progress, actions, decisions, risks, blockers, and gaps. | Context Pack. Optional: recent Daily Notes, minutes, or action plan. |
| [Thinking Interview](thinking-interview.md) | Runs a one-question-at-a-time interview to help you develop your own position before synthesis. | None required. Optional: rough note, Context Pack, or draft. |
| [Voice](voice.md) | Builds or updates a practical writing voice guide from approved writing samples. | Approved writing samples. Optional: existing voice guide or declared preferences. |
| [Resolve Document Items](resolve-document-items.md) | Works through unresolved questions, placeholders, unowned tasks, assumptions, and pending decisions one item at a time. | Document containing unresolved items. Optional: Context Pack or Daily Note. |

## How To Use A Skill

1. Open the skill file.
2. Read the **Required Inputs** and **Optional Inputs**.
3. Upload those documents into your LLM chat.
4. Copy and paste the full prompt from the skill.
5. Review the answer.
6. Save any complete replacement documents into the folder named by the skill.

## Important Rules

- If a document was not uploaded, the LLM must not pretend to update it.
- If a document is updated, the LLM should return a complete replacement document, not a patch.
- The LLM must not invent facts, decisions, owners, due dates, or actions.
- Uncertainty should be surfaced clearly.
- Your local vault is the durable record, not the chat thread.
