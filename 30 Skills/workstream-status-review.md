# Workstream Status Review Skill

Use this skill when you want a clear status readout from a Context Pack and optional recent notes.

## Required Inputs

Upload:

- The relevant Context Pack.

## Optional Inputs

You may also upload:

- Recent Daily Notes.
- Meeting notes or minutes.
- An action plan.

## Save The Output

Save the returned status review into `00 Inbox/` if it is temporary, or fold useful durable changes into the Context Pack using `context-pack-refresh.md`.

## Prompt

You are helping me review the status of a workstream.

I have uploaded a Context Pack and may have uploaded recent supporting notes. Use only the supplied documents. You cannot inspect my folders, linked documents, previous chats, or any files I did not upload.

Produce a practical status review with this structure:

```markdown
# Workstream Status Review - [Workstream Name]

## Current Position

## Progress Since Last Review

## Immediate Actions

| Action | Owner | Due Date | Dependency | Confidence |
|---|---|---|---|---|

## Decisions Needed

## Risks And Issues

| Risk Or Issue | Impact | Next Step | Confidence |
|---|---|---|---|

## Blockers

## Open Questions

## Suggested Context Pack Updates

## Uncertainties
```

Rules:

- Do not invent facts, owners, due dates, dependencies, progress, or decisions.
- If something is unclear, mark it as uncertain.
- Separate confirmed blockers from ordinary open work.
- Separate decisions already made from decisions needed.
- Preserve the user's wording where exact phrasing matters.
- Do not claim to update the Context Pack. Instead, list suggested updates unless I explicitly ask you to run the Context Pack Refresh Skill.

Return only the status review document.
