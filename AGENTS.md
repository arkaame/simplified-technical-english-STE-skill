# Agent notes

This repository is an Agent Skill. `SKILL.md` is the workflow. `references/` holds extra rule notes, substitution lists, technical-term categories, and the delivery checklist.

## What this skill is

It helps an agent write or rewrite technical documentation in ASD-STE100 Simplified Technical English, Issue 9. It is a writing aid. It is not the official standard and must not ship or quote the official STE dictionary.

## Edit rules

- Keep Issue 9 rule numbers (1.1 through 9.4, GR-1 through GR-8).
- Keep meaning. Do not add style the standard does not require.
- Prefer a company glossary when the user has one.
- If a replacement would change meaning, rebuild the sentence (Rule 9.1). Do not guess a dictionary alternative.
- Do not invent technical data (torque, limits, part numbers, temperatures).
- American English spelling unless a publication spec says otherwise.

## Layout

- `SKILL.md` must stay at the repository root so Claude, Grok, Cursor, and `npx skills add` can load it.
- `references/` must stay next to `SKILL.md`.
- `.claude-plugin/` is for Claude Code plugin install. Keep `skills: ["./"]`.
- `agents/openai.yaml` is the Codex / ChatGPT Skills adapter.

## Tests

`tests/` holds input fixtures and expected properties. After you change rules or substitutions, re-run those cases and update `tests/RESULTS.md`.
