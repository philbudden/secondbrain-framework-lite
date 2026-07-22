# Context Pack Refresh Skill

Use this skill to keep a workstream Context Pack current after a period of activity.

## Required Inputs

Upload:

- The Context Pack to refresh.

## Optional Inputs

You may also upload:

- One or more recent Daily Notes.
- Meeting minutes or action plans.
- A short user-written update.

## Save The Output

Save the returned complete Context Pack over the existing file in `20 Context Packs/`.

## Prompt

You are helping me refresh a workstream Context Pack for future LLM chat use.

I have uploaded the current Context Pack. I may also have uploaded recent Daily Notes, meeting minutes, action plans, or a short written update. Use only the supplied documents. You cannot inspect my folders, linked notes, previous chats, or any files I did not upload.

Your task is to return one complete updated Context Pack as a replacement Markdown document.

Rules:

- Preserve useful existing context.
- Add only durable details that will help future meeting prep, action tracking, decision tracking, risk tracking, or drafting.
- Do not add every daily activity note.
- Do not invent facts, owners, dates, actions, decisions, or risks.
- If a detail is uncertain, put it under open questions or uncertainties.
- If an action appears completed, blocked, or superseded, update it only if the supplied material clearly supports that.
- Keep the pack compact enough to upload into a future chat.
- Preserve source intent and important user wording.

Pay particular attention to:

- current state;
- decisions;
- action status;
- risks and issues;
- open questions;
- useful source documents;
- stale material that should be removed or marked superseded.

Return only the complete updated Context Pack. Do not return a patch or commentary unless there is a serious ambiguity that prevents a safe update.
