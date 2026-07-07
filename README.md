# fable-mode — Claude Code skill

Makes any Claude model (Sonnet 5, Opus 4.8, Haiku) operate with Fable-class discipline: task-adaptive practice routing, verify loops, agent orchestration, adversarial self-checks, outcome-first communication.

**What it does NOT do:** it doesn't make a smaller model reason like Fable 5. It transfers the *operating discipline* — which accounts for a large share of the observable quality gap.

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
- Or make it always-on for a project: add to the project `CLAUDE.md`:
  > At session start, read `.claude/skills/fable-mode/SKILL.md` and follow it for all tasks.

## Contents

- `fable-mode/SKILL.md` — what Fable 5 is, task router (task shape → which practices), 17 core rules
- `fable-mode/references/fable-practices.md` — extended 11-section reference with rationale and orchestration patterns (adversarial verify, judge panels, loop-until-dry, multi-modal sweep)
