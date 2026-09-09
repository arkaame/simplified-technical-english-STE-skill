# Simplified Technical English

Rewrite technical documentation so a reader with limited English can understand it on the first pass. The skill follows ASD-STE100 Issue writing rules. Because it is Markdown, it works with Grok, Claude, Cursor, and any other agent that loads skills.

This skill is a writing aid. It is not the official ASD-STE100 standard and does not replace the official STE dictionary.

## Installation

### Skills CLI (Grok, Claude Code, Cursor, Codex, and others)

```
npx skills add arkaame/simplified-technical-english --global
```

Leave off `--global` to install only in the current project. Add `--agent grok`, `--agent claude-code`, or `--agent '*'` to choose which agents receive it, then reload their skills.

The skill answers to `/simplified-technical-english`.

### Grok (manual)

Copy this folder to the Grok skills directory:

- macOS / Linux: `~/.grok/skills/simplified-technical-english/`
- Windows: `%USERPROFILE%\.grok\skills\simplified-technical-english\`

Keep `SKILL.md` and the `references/` folder together. Reload Grok skills after the copy.

### Claude Code plugin

```
/plugin marketplace add arkaame/simplified-technical-english
/plugin install simplified-technical-english@simplified-technical-english
```

The plugin answers to `/simplified-technical-english:simplified-technical-english`.

### Claude Desktop

Download this repository as a ZIP and upload it as a skill. GitHub's source ZIP already has `SKILL.md` at the root, which Claude Desktop expects.

### Cursor

Copy this folder to `~/.cursor/skills/simplified-technical-english/` (all projects) or `.cursor/skills/simplified-technical-english/` (this project only).

### Manual

Copy `SKILL.md` and `references/` into the agent's skill folder. Do not copy `SKILL.md` without `references/`.

## Usage

Call the skill directly:

```
/simplified-technical-english

[paste a procedure, description, warning, or manual topic]
```

Or ask in plain language:

```
Rewrite this maintenance procedure in Simplified Technical English:

[paste your text]
```

To convert a file, give the skill its path:

```
Convert docs/bleed-valve.md to STE
```

### Review mode

Ask for a review when you want rule numbers, not only a rewrite:

```
Review this text against ASD-STE100 and list the violations
```

### Company glossary

If you have approved technical nouns or verbs, paste them or point to the glossary. The skill uses those names instead of inventing alternatives.

## How it works

STE limits the words, verb forms, and sentence shapes a writer may use so a reader who is not a native English speaker can follow a procedure without rereading.

The skill:

1. Identifies the text type (procedure, description, safety instruction, or note)
2. Keeps the technical meaning. It does not invent data, limits, part numbers, or risks
3. Applies Issue rules in order: words, noun strings, verbs, sentence shape, type-specific limits, punctuation, then consistency
4. Replaces unapproved wording from `references/substitutions.md`, or rebuilds the sentence if a swap would change meaning
5. Counts words with the Section 8 method (20 words for procedures, warnings, and cautions; 25 words for descriptions and notes)

It does not force STE on marketing copy, narrative prose, or legal argument unless you ask.

## Example

Before:

Don't start the engine until you've performed a check of the oil level. Ensure the drain valve is closed. Then turn on the fuel pump and verify that pressure is indicated. If you see leakage, you should immediately terminate the test.

After:

1. Before you start the engine, do a check of the oil level.
2. Make sure that the drain valve is closed.
3. Set the fuel pump to ON.
4. Make sure that the pressure is shown.
5. If you see leakage, stop the test immediately.

## What this skill does not include

The official ASD-STE100 dictionary is copyrighted. This repository ships a working subset of frequent replacements and the technical noun / technical verb categories. Use the official dictionary and your company glossary for production manuals.

## Tests

See `tests/` for the fixture set used to check the skill.

## License

MIT
