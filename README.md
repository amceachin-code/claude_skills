# Claude Code Skills

Three custom skills for [Claude Code](https://docs.anthropic.com/en/docs/claude-code), Anthropic's CLI tool. Each skill extends Claude's capabilities for specific review and editing tasks.

## Skills

### writing-style

A sentence-level prose editor grounded in Verlyn Klinkenborg's *Several Short Sentences About Writing*. It reads your text (inline, from a file, or from a URL), then revises it in three passes: clarity, agency, and structure. The goal is control over what each sentence does, not decoration.

```
/writing-style <text>      # Edit inline text
/writing-style <path>      # Edit content from a local file
/writing-style <url>       # Edit content from a web page
```

### datascience-reviewer

Code review from the perspective of a senior data scientist. Evaluates engineering quality across five dimensions: structural issues, correctness risks, efficiency concerns, usability, and maintainability. Tags every finding with a severity level (BLOCKING, IMPORTANT, MINOR) and ends with a prioritized list of concrete changes.

```
/datascience-reviewer <path>    # Review a specific file or directory
/datascience-reviewer           # Review the current project
```

### methods-reviewer

Methodological review from a causal inference and semiparametric statistics perspective. Challenges identification assumptions, estimation strategies, and finite-sample claims. Useful for stress-testing research methodology before presenting to expert audiences.

```
/methods-reviewer <path>     # Review a specific file
/methods-reviewer <topic>    # Challenge a specific methodological decision
/methods-reviewer            # Review the current project's methodology
```

## Shared Resources

The `shared/` directory contains reference documents that skills import during their review process:

- **AI-TELLS.md**: Words, phrases, and structural patterns that signal AI-generated content. Skills reference this to avoid producing text that reads as obviously machine-written.
- **WRITING-PRINCIPLES.md**: Principles distilled from Klinkenborg's book. Provides the revision checklist and core concepts that the writing-style skill (and other skills) use when generating or editing prose.

## Installation

### Option 1: Copy the files

Copy the skill directories into your Claude Code skills folder:

```bash
cp -r writing-style ~/.claude/skills/
cp -r datascience-reviewer ~/.claude/skills/
cp -r methods-reviewer ~/.claude/skills/
cp -r shared ~/.claude/skills/
```

### Option 2: Symlink from the cloned repo

```bash
git clone https://github.com/amceachin-code/claude_skills.git
ln -s "$(pwd)/claude_skills/writing-style" ~/.claude/skills/writing-style
ln -s "$(pwd)/claude_skills/datascience-reviewer" ~/.claude/skills/datascience-reviewer
ln -s "$(pwd)/claude_skills/methods-reviewer" ~/.claude/skills/methods-reviewer
ln -s "$(pwd)/claude_skills/shared" ~/.claude/skills/shared
```

### Skill lookup

For Claude Code to find these skills automatically, your project or global `CLAUDE.md` needs a custom skill lookup section that searches `~/.claude/skills/`. See [Claude Code documentation](https://docs.anthropic.com/en/docs/claude-code) for details on configuring skill discovery.

## Note on Symlinks

This repository uses symlinks that point to absolute paths on the maintainer's machine. If you clone this repo, the symlinks will not resolve on your system. Use one of the installation options above instead. The symlink structure exists so that edits to the source files are immediately reflected in the repo without manual copying.

## Repository Structure

```
claude-skills/
├── README.md
├── .gitignore
├── shared/
│   ├── AI-TELLS.md
│   └── WRITING-PRINCIPLES.md
├── writing-style/
│   └── SKILL.md
├── datascience-reviewer/
│   └── SKILL.md
└── methods-reviewer/
    └── SKILL.md
```
