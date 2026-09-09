# 07 review — expected properties

Mode: review.

Must return:

1. STE rewrite
2. Findings with location, non-STE wording, rule number, and fix
3. Word-count flags if a sentence is over the limit

Findings that must appear (rule numbers may be grouped if one phrase breaks several rules):

- `Don't` — contraction — 4.2
- `utilize` — unapproved / use USE — 1.1 / substitutions
- semicolon — 8.1
- `ensure` — MAKE SURE THAT — 1.1 / 9.2
- omitted `that` after make sure if it survives — GR-1
- `e.g.` and `etc.` — GR-6
- `You must perform` on an ordinary command — prefer imperative; `perform` → DO
- `prior to` → BEFORE
- Color `yellow` is a technical noun (permitted)

Do not fail the case if extra valid findings are listed.
