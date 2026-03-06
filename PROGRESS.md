# Progress

## Task: Set Up Claude Skills GitHub Repository

**Date**: 2026-03-05
**Status**: Complete
**Repo**: https://github.com/amceachin-code/claude_skills.git

### Objective

Create a GitHub repository containing 3 Claude Code custom skills (writing-style, datascience-reviewer, methods-reviewer) and 2 shared resource files, using symlinks so the source of truth remains at `~/Desktop/.claude/skills/`.

### Steps

| # | Step | Status |
|---|------|--------|
| 1 | Clone empty repo from GitHub | Done |
| 2 | Create subdirectories (shared, writing-style, datascience-reviewer, methods-reviewer) | Done |
| 3 | Create 5 symlinks to source files in ~/Desktop/.claude/skills/ | Done |
| 4 | Write README.md with skill descriptions, installation instructions, repo structure | Done |
| 5 | Write .gitignore (.DS_Store, .Rhistory) | Done |
| 6 | Commit and push (commit 16bc6eb) | Done |

### Files Created

- `README.md`
- `.gitignore`
- `shared/AI-TELLS.md` -> `~/Desktop/.claude/skills/shared/AI-TELLS.md`
- `shared/WRITING-PRINCIPLES.md` -> `~/Desktop/.claude/skills/shared/WRITING-PRINCIPLES.md`
- `writing-style/SKILL.md` -> `~/Desktop/.claude/skills/writing-style/SKILL.md`
- `datascience-reviewer/SKILL.md` -> `~/Desktop/.claude/skills/datascience-reviewer/SKILL.md`
- `methods-reviewer/SKILL.md` -> `~/Desktop/.claude/skills/methods-reviewer/SKILL.md`
