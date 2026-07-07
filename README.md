# fable-mode: Claude Code skill

Makes any Claude model (Sonnet 5, Opus 4.8, Haiku) operate with the discipline of Anthropic's flagship Fable 5: task-adaptive practice routing, verify loops, agent orchestration, adversarial self-checks, outcome-first communication.

**Honest framing — what this does and doesn't do:** it does **not** make a smaller model reason like Fable 5; no prompt can transfer raw intelligence. What it transfers is *operating discipline* — how the model verifies its work, delegates, self-checks, and communicates — which accounts for a large share of the observable quality gap between a default Sonnet session and a Fable session.

## What changes in practice

- **Verifies before claiming "done"** — runs the change end-to-end (test, endpoint, page), quotes real output. "It compiles" is never verification.
- **Double-checks its own findings** — bugs and audit results go through an adversarial refutation pass before being reported; unproven findings die silently instead of reaching you.
- **Stops scope creep** — every changed line must trace to your request; no drive-by refactors or "improvements" you didn't ask for.
- **Routes discipline by task shape** — a quick question gets a direct answer; an audit gets fan-out finders, multi-vote verification, and loop-until-dry coverage. No overhead where it doesn't pay.
- **Reports failures honestly** — failing tests quoted, skipped steps named, bounded coverage disclosed.

Biggest lift is on Sonnet 5 doing multi-step work (features, debugging, reviews). Near-zero gain on one-shot trivia questions — by design.

## Install

Pick one:

**Personal (all your projects):** copy the `fable-mode/` folder into `~/.claude/skills/`
```powershell
Copy-Item -Recurse fable-mode "$env:USERPROFILE\.claude\skills\fable-mode"
```
```bash
cp -r fable-mode ~/.claude/skills/fable-mode
```

**Per-project (shared via repo):** copy `fable-mode/` into the repo's `.claude/skills/` and commit. Everyone who clones gets it.

## Use

- Type `/fable-mode` in any Claude Code session — discipline persists until session end or "fable mode off".
- **Auto-fire on complex tasks (recommended):** add this to your `~/.claude/CLAUDE.md`:
  > Invoke the `fable-mode` skill before starting any task that is: a multi-file code change, debugging with no obvious cause, a review/audit/"be thorough" request, multi-source research, or anything expected to take more than ~5 tool calls. Skip for single-fact questions and trivial edits. Don't re-invoke if already active this session.

## Contents

- `fable-mode/SKILL.md` — what Fable 5 is, a task router (task shape → which practices apply), and 17 always-on core rules
- `fable-mode/references/fable-practices.md` — extended 11-section reference with rationale and orchestration patterns (adversarial verify, judge panels, loop-until-dry, multi-modal sweep)

## License

MIT — see [LICENSE](LICENSE). If this is useful, a star helps me know it's worth maintaining.
