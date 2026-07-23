# SecondBrain Framework Lite

SecondBrain Framework Lite is a plain-Markdown knowledge-management framework for people who work with an ordinary LLM chat interface. It assumes the user can keep a simple local folder of notes, upload selected documents into chat, paste reusable prompts, and save the model's returned Markdown back into the right place.

It does not require agents, scripts, Python, package managers, automation, browser access, folder inspection, direct file editing by the model, a specific note-taking app, or a specific AI provider.

## Folder Structure

```text
00 Inbox/
10 Daily/
20 Context Packs/
30 Skills/
90 Archive/
```

The constraint is deliberate: a small system is easier to maintain, easier to explain to a chat model, and less likely to become a dumping ground.

## How This Works With Chat

The LLM cannot see your vault unless you upload or paste material. Each skill prompt tells you which documents to upload. When a skill updates a document, it should return a complete replacement Markdown document. You then save that returned document over the old one in your local vault.

Basic workflow:

1. Open the relevant skill in `30 Skills/`.
2. Upload the documents listed in the skill's **Inputs** section.
3. Copy and paste the full prompt from the skill into chat.
4. Review the answer carefully.
5. Save any complete replacement documents into the folder named by the skill.

Do not ask the LLM to update files that you did not upload. Do not rely on the chat history as your durable record. Important decisions, actions, risks, and context should end up in a Daily Note or Context Pack.

## Design Principles

- Useful structure beats complex tooling.
- Daily Notes hold day-specific activity and actions.
- Context Packs hold durable workstream context.
- Skills are reusable prompts, not software.
- The user remains responsible for judgement, review, and saving documents.
- Durable context should be compact, current, and useful in future chats.

## Skill Menu

The reusable prompts live in `30 Skills/`. Start with the menu below, then open the skill file you need.

| Skill | Use It When You Want To |
|---|---|
| `daily-note-rollover.md` | Create today's Daily Note from yesterday's note. |
| `meeting-prep.md` | Prepare for a meeting using a Context Pack and optional Daily Note. |
| `live-meeting-copilot.md` | Use a preloaded briefing pack for fast, concise typed support during a live meeting. |
| `actions-from-meeting.md` | Turn meeting notes or a transcript into actions, decisions, updated context, and an optional Daily Note update. |
| `minutes.md` | Produce structured meeting minutes from rough notes or a transcript. |
| `context-pack-refresh.md` | Refresh durable workstream context from recent activity. |
| `workstream-status-review.md` | Get a clear status readout from a Context Pack and recent notes. |
| `thinking-interview.md` | Develop your own thinking through a one-question-at-a-time interview. |
| `voice.md` | Analyse approved writing samples and create or update a practical voice guide. |
| `resolve-document-items.md` | Work through unresolved questions, placeholders, owners, and actions in a document. |

## Getting Started

1. Copy `10 Daily/daily-note-template.md` to `10 Daily/YYYY-MM-DD.md`.
2. Create one Context Pack from `20 Context Packs/context-pack-template.md` for an active workstream.
3. Use `30 Skills/daily-note-rollover.md` each morning to create today's Daily Note from yesterday's note.
4. Use `30 Skills/meeting-prep.md` before a meeting, `30 Skills/live-meeting-copilot.md` during it when useful, and `30 Skills/actions-from-meeting.md` after it.
5. Refresh Context Packs when meetings, decisions, risks, or action state materially change.
