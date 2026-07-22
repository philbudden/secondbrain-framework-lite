# 30 Skills

Skills in this framework are reusable prompts. They are not software, scripts, plugins, agents, or automations.

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
