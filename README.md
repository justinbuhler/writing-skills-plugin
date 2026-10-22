# writing-skills

A Claude Code plugin with 10 writing skills for consulting documents, technical procedures, and strategic communications.

## Install

In Claude Code:

```
/plugin marketplace add justinbuhler/writing-skills-plugin
/plugin install writing-skills@writing-skills
```

Or from the shell:

```
claude plugin marketplace add https://github.com/justinbuhler/writing-skills-plugin
claude plugin install writing-skills@writing-skills
```

## Skills

### Orchestrator

| Skill | When to use |
|---|---|
| `writing-workflow` | Full document production — sequences all relevant skills in order |

### Structure

| Skill | When to use |
|---|---|
| `scqa-framework` | Opening hook and governing thought (Situation → Complication → Question → Answer) |
| `scr-narrative` | Full narrative spine for long strategic documents (Situation → Complication → Resolution) |
| `pyramid-editor` | Body structure and logical flow — answer first, evidence below |
| `recommendations-and-actions` | Audit findings, recommendations, decisions required, and action items |

### Language

| Skill | When to use |
|---|---|
| `plain-language` | Reports, memos, policy documents, stakeholder communications |
| `ste100-writer` | Technical procedures, maintenance manuals, work instructions, safety notices |
| `humanizer` | Remove AI writing patterns from AI-drafted documents |
| `no-ai-slop` | Sharpen voice and cut editorial slop from any flat draft |

### Quality gate

| Skill | When to use |
|---|---|
| `document-qa` | Final pre-delivery check — structure, audience fit, completeness, accuracy |

---

## Writing workflow

For full documents, use `writing-workflow` instead of invoking skills individually. It sequences the right skills in order and passes each step's output into the next.

```
1. narrative framing   →  scqa-framework  (most documents)
                          scr-narrative   (long strategic documents)
2. pyramid-editor      →  body structure and logical flow
3. recommendations-and-actions  →  skip if document has no findings
4. language review     →  plain-language  (reports, memos, comms)
                          ste100-writer   (procedures, manuals)
4.5 humanizer (optional)   →  AI-drafted documents
4.6 no-ai-slop (optional)  →  any draft that feels flat
5. document-qa         →  final pre-delivery gate
```

For routing decisions — when to use which skill at each step — see [`skills/writing-workflow/routing-guide.md`](skills/writing-workflow/routing-guide.md).

---

## Tests

Each skill has a `TESTS.md` with RED/GREEN test cases. RED contains text that violates the skill's rules; GREEN is the corrected version. The expected finding states exactly what the skill should flag.

| Skill | Tests |
|---|---|
| document-qa | 28 |
| humanizer | 33 |
| no-ai-slop | 28 |
| plain-language | 35 |
| pyramid-editor | 20 |
| recommendations-and-actions | 27 |
| scqa-framework | 21 |
| scr-narrative | 23 |
| ste100-writer | 41 |
| writing-workflow | 25 |

---

## Standards

- `plain-language` follows plain language principles as applied in consulting and policy writing.
- `ste100-writer` implements ASD-STE100 Issue 9 (January 2025) from summaries written for this repository. The standard itself is © ASD and is not included. Where the skill and the standard disagree, the standard is correct. You can request a free copy at [asd-ste100.org](https://asd-ste100.org). ASD-STE100 is a trademark of ASD; this project is not affiliated with or endorsed by ASD.
- `pyramid-editor` applies the Minto Pyramid Principle.
- `scqa-framework` and `scr-narrative` apply McKinsey-style narrative structuring.

## License

MIT. See [LICENSE](LICENSE). `skills/humanizer/` is a fork of [blader/humanizer](https://github.com/blader/humanizer) and keeps its own MIT [LICENSE](skills/humanizer/LICENSE).
