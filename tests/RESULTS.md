# Test results

Skill version 1.0.0. Fixtures were converted by an agent that was allowed to read only `SKILL.md` and `references/`.

| Case | Result | Notes |
|---|---|---|
| 01 procedure | Pass | Kept the "before you start the engine" condition. Split pump ON and pressure check. |
| 02 description | Pass | Active voice, no imperative, "dangerous" not upgraded to injury. |
| 03 safety | Pass | Grease/oxygen relabeled WARNING; battery/cards relabeled CAUTION. |
| 04 word class | Pass | `Do a test of` / `Obey` / `Do a check of`. |
| 05 technical verbs | Pass | Matches the skill examples for grease, clamps, and find vs detect. |
| 06 word count | Pass | Split the long sentence; kept `EMER`; stayed under 20 words. |
| 07 review | Pass | Rewrite plus findings with rule numbers (4.2, 1.1, 8.1, GR-1, GR-6, 5.2, GR-3). |
| 08 negative marketing | Pass | Did not force STE. |
| 09 missing facts | Pass after skill patch | First run added `specified torque` although the source never mentioned torque. The invent-data rule was tightened. Retest kept `PN` and did not invent a number. |

## Skill changes from tests

- Version set to `1.0.0`.
- File mode and embedded mode added.
- Invent-data rule: do not add `specified torque` unless the source mentions a specification.
- Substitutions: `indicated` → SHOW; `keep away from` → DO NOT APPLY / DO NOT PUT ON.

Outputs are in `tests/actual/`.
