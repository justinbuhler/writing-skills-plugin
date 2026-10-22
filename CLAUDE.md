# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Validation and testing

**Validate the plugin manifest:**
```bash
claude plugin validate .
```

**Check skill discovery:**
```bash
npx --yes skills@1.5.20 add . --list
```

**Validate the humanizer package** (run from `skills/humanizer/`):
```bash
python3 scripts/validate-package.py
```

**Run tests for a single skill** — launch a Claude agent with this prompt:
> Read `skills/<name>/SKILL.md` and `skills/<name>/TESTS.md`. For each test, apply the skill's rules to the RED text and compare your finding to the Expected finding. Report Total X/Y passed and list any FAILs.

**Run all 10 skills in parallel** — launch one agent per skill simultaneously with the above prompt. Re-run after any fix until X/X with no discrepancies noted. "PASS with discrepancy noted" is not clean.

## What gates a change

GitHub Actions is not used: this repo buys no Actions credits. Both workflows in `.github/workflows/` are manual-only (`workflow_dispatch`), `main` has no branch protection, and red or missing Actions checks never block a commit or merge. Do not restore their push or pull-request triggers.

`.githooks/pre-push` is the only gate. `core.hooksPath` is local git config and cannot be committed, so a `SessionStart` hook in `.claude/settings.json` sets it each time a Claude Code session opens here. **Outside Claude Code it stays off** — run `git config core.hooksPath .githooks` once per clone, or pushes go out unchecked. To change what is enforced, edit that hook and the matching workflow together so they stay in step.

One check catches people: `.claude-plugin/plugin.json`'s `skills[]` must equal the `skills/*/` directories exactly — set equality, not a subset. A skill directory without a manifest entry fails, and so does the reverse.

## Architecture

This is a Claude Code plugin. There is no build step — all content is markdown.

**Plugin manifest:** `.claude-plugin/plugin.json` lists the 10 skill directories. `.claude-plugin/marketplace.json` is what makes `claude plugin marketplace add <repo-url>` work; it points at `./` as a single plugin source.

**Skill structure:** Each skill directory contains:
- `SKILL.md` — YAML frontmatter (`name`, `description`, `allowed-tools`) followed by the instruction body. The `description` is the primary triggering mechanism — it determines when Claude loads the skill.
- `TESTS.md` — RED/GREEN test pairs (see below).
- `references/` — optional reference files the skill loads on demand (only `ste100-writer` uses this).

**Skills are read-only reviewers.** Nine of the ten declare `allowed-tools: Read`. A skill returns findings or rewritten prose in its response; it never edits the user's files. Preserve this when adding a skill. `humanizer` is the exception and must stay that way — its validator rejects the field (see below).

**Review-or-rewrite contract:** most skills open with a `## Two jobs` section splitting a review pass (report findings, change nothing) from a rewrite pass. A skill that only ever rewrites is the odd one out — match the surrounding convention.

**Orchestrator pattern:** `writing-workflow` is the only orchestrator skill. It sequences the other skills by name. The orchestrator states what sub-skill to invoke and what to pass — it does not reproduce the sub-skill's internal procedure. Each sub-skill's `SKILL.md` owns its own operating contract.

**Routing reference:** `skills/writing-workflow/routing-guide.md` is a human planning reference for the workflow. `SKILL.md` contains the executable instruction for the model. Some overlap between them is intentional — they serve different audiences.

**Cross-harness adapters:** `skills/humanizer/agents/openai.yaml` and `skills/no-ai-slop/agents/openai.yaml` expose those two skills to non-Claude harnesses. Nothing in this repo reads them; leave them alone unless changing the skill's public name or one-line pitch.

## The humanizer subtree is a fork, not a mirror

`skills/humanizer/` is a fork of [blader/humanizer](https://github.com/blader/humanizer) taken at tag `v3.0.0`. It carries its own `LICENSE`, `README.md`, `AGENTS.md`, `.claude-plugin/`, `.github/workflows/`, and `scripts/`. It was copied in by hand, never added via `skills add` and never a git subtree or submodule, so nothing tracks upstream automatically. We do not send changes upstream.

**The fork differs from the tag in `TESTS.md`, 45 `SKILL.md` hunks, and 5 `README.md` hunks, all deliberate:**

1. `TESTS.md` — our test suite; upstream has none.
2. `SKILL.md:362` — the *weak alone* gate, rewritten to remove an ambiguity in upstream v3.0.0.
3-6. `SKILL.md` §4, §12, §18, §20 — each `After:` block invented facts its `Before:` never supplied, which the skill's own `:31`/`:36`/`:37` forbid; §20's manufactured "User research showed" also breaks `:17` "never invent a source". Found 2026-09-15 when three skills' test GREENs turned out to be imitating these examples.
7-14. `SKILL.md:36` keeps other skills' `[needs: …]` gap markers; `:188` forbids inventing an actor for a passive; the `After:` blocks at §3 `:103`, §6 `:145`, §11 `:192`, §17 `:262`, §19 `:289`, §25 `:358` invented details. Found 2026-09-22 by a functional review.
15. The rest of that review (2026-09-23): code, links, quotations and tables are protected in every mode (`:33`); dated status lines, definitions, real requests and range dashes are kept (§23, §19, §22, §8); literal and technical uses of listed words are exempt (§3, §10, §12); one §12 word is *weak alone*; a footnote names a source (§17); clean text comes back unchanged (`:48`); the description no longer claims filler (`:7`). `README.md:75`, `:79`, `:98`, `:100`, `:106` match.
16. The 2026-10-22 review: `:29` says unmarked patterns act on one clear sighting; the §1 `:65`, `:69` and `:73`, §2 `:82`, §3 `:103` and `:107`, §6 `:145` and `:149`, §12 `:205`, §13 `:214` and `:218`, §14 `:231`, §15 `:240`, §17 `:258` and §19 `:289` `After:` blocks no longer add or drop details, and §8 `:166` no longer leaves a §17 tell; `:362` says worked examples show how to rewrite once a gate is met, not when to act; §11 `:188` allows "you" where the text addresses the reader; §12 `:200-201` admits its overlap with §13, §15, §16 instead of claiming to be the only list; §17 `:254` says to put a footnoted source's name in the sentence. `README.md:106` matches.

To verify nothing else has drifted, extract the tag and run `diff -r <tag-dir> skills/humanizer`. Expect `Only in skills/humanizer: TESTS.md` plus 45 `SKILL.md` hunks and 5 `README.md` hunks, and nothing more.

**Why `:362` diverges.** Upstream states the gate twice and the two admit different readings. `:29` says a `*Weak alone.*` pattern "needs company from **other** tells"; `:362` said "only when **several tells** share a passage". Four passive constructions in one passage satisfy the second but not the first, so the same text yields opposite outputs depending on which line you read. §8's inline carve-out ("one dash is *weak alone*; a text full of them is not") only makes sense if repetition normally does *not* clear the gate, which is what settles it in favour of `:29`. Our `:362` now says so explicitly and names §8 as the sanctioned exception. Six patterns carry the marker: §8 (with its own carve-out), §9, §10, §11, §12, §21. §25 does not, and never did upstream.

**Pulling a future upstream release is now a merge, not a copy.** Re-apply the `:362` change and the other `SKILL.md` and `README.md` hunks (items 3-16 above) by hand, dropping any that upstream has fixed itself. Do not overwrite the subtree wholesale without checking which hunks survived.

Edits here answer to upstream's validator, not this repo's conventions. `scripts/validate-package.py` hard-fails on:

- Frontmatter containing `version:`, `compatibility:`, or `allowed-tools:` at the top level — **the rest of this repo sets `allowed-tools: Read`; humanizer forbids it.** Do not "fix" humanizer for consistency. The version lives at `metadata.version`.
- A version that is not identical in all three of: `SKILL.md` frontmatter `metadata.version`, the first `- **X.Y.Z**` line in `README.md`, and `.claude-plugin/plugin.json`.
- `### N.` pattern headings in `SKILL.md` that are not `1..N` contiguous, README `| N |` rows that do not match them exactly, or a README missing the literal heading `## The N patterns`.
- More than one `SKILL.md` anywhere under `skills/humanizer/`, or a symlinked one.
- `SKILL.md` over 400 lines.

**Upgrading humanizer renumbers the test suite.** `TESTS.md` headings and `[N label]` finding tags are keyed to the pattern numbers, and upstream renumbers on a major bump — v3.0.0 went from 35 patterns to 25, mostly by renaming and merging rather than deleting, with only 7 titles carried over verbatim.

Read the changelog entry in `skills/humanizer/README.md` first: upstream publishes an authoritative old-to-new map there (the v3.0.0 entry ends `Old to new numbers: 1→13, 2→17, …`). Use it instead of inferring the mapping, and check the pattern body before accepting an entry — `Vague sources` reads like `14 Vague connection or association` but is actually `17 Borrowed authority`, whose watch list carries `experts argue, industry reports`. When a pattern maps to `dropped`, delete the test and record it in the "Tests dropped" table in `TESTS.md` rather than leaving a case that can never pass.

**Never carry a test's RED or GREEN across an upgrade unchecked.** Upstream absorbs real-world examples into `SKILL.md` as `**Before:**` blocks, so a RED that was original under the old version becomes a near-copy of a worked example under the new one — testing recall, not application. Four checks are needed, and each one missed defects the next caught:

- Longest shared word-run against every `Before:` block. Catches lifts that a global similarity ratio scores low.
- Function-word skeleton similarity. Catches slot-swaps, where content words are replaced but the sentence template survives — these have short word-runs by construction.
- GREEN vs RED for added figures, dates, proper nouns, and *spelled-out* numbers. A digits-only check misses "Two of the four workstreams".
- Every GREEN against every *other* pattern's watch-for list. A GREEN that fixes its own pattern can trip a different one.

None of these catch meaning drift — "by June" becoming "in June" narrows a claim while adding and removing nothing. That needs a claim-by-claim read. Run the per-skill test agent and treat it as the real gate; the scans only decide where it should look.

**Re-derive a GREEN whenever you rewrite its RED.** Fixing one defect class seeds another: rewriting a RED to break a clone silently invalidates the GREEN that was written against the old content.

**Check a test against its pattern's activation conditions, not just its rule.** A pattern marked `*Weak alone.*` needs other tells in the same passage before the skill acts, so a RED demonstrating only that pattern asserts a finding the skill would correctly refuse to produce.

**Leave `skills-lock.json` empty.** Commit `806c4a3` set the policy: once a vendored skill diverges from its upstream source, drop its lock entry and treat it as locally owned, because the tracked hash stops meaning anything. An entry would also need a `computedHash` only the `skills` CLI can produce — do not hand-write one.

## Test format

Every `TESTS.md` uses this structure:

```
**RED:** <violating text — should be flagged>
**GREEN:** <corrected version — should pass>
**Expected finding:** `[rule/area] <exact string the skill should produce>`
```

When writing Expected findings: verify any specific counts (word counts, sentence counts, item counts) against the actual RED text before committing. A mismatched count causes FAIL even when the rule violation is correct.

**Humanizer TESTS.md** uses §-numbered sections that map to the skill's internal pattern catalogue (1–25 as of v3.0.0). Gaps mean no test case exists for that pattern — not missing or deleted tests. Note the asymmetry: `TESTS.md` sections may be sparse, but `SKILL.md` pattern headings must run 1–N with no gaps.

## Key conventions

- `ste100-writer` implements ASD-STE100 Issue 9 from its own summaries in `references/`. The standard is © ASD: never commit its text, and keep the summaries in our own words (no run of 12 or more words matching the standard). Rule numbers and page citations are fine. The pre-push hook checks every cited rule number against the `rules.md` headings.
- When a test agent reports a FAIL, determine whether the error is in the test file (wrong rule citation, wrong count) or the skill file (missing rule content) before editing.
- Keep each `SKILL.md` under 500 lines. Put deep specifications and long examples in `references/` and link from the skill. Only humanizer's limit is machine-enforced; the rest is discipline.
- `skills/no-ai-slop/eval.md` is a post-rewrite self-check the skill runs against its own output — not a test file and not covered by the agent test procedure above.
