<div align="center">

# ai-rules-cn

**Ready-to-use Chinese rule files for AI coding assistants**

Make your AI assistant speak Chinese, follow conventions, and stop touching code it shouldn't

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/Mr404-404/ai-rules-cn/pulls)

[简体中文](README.md) | English

</div>

---

## What is this

A collection of **Chinese-language rule files** you can drop into any project to configure AI coding assistants:

- **AGENTS.md** — Antigravity, Kimi Code, Codex, and other AGENTS.md-compatible tools
- **CLAUDE.md** — Claude Code
- **.cursorrules** — Cursor

Without rules, AI assistants tend to reply in English, write verbose comments, refactor unrelated code, and produce chaotic commit messages. A rule file in the project root makes the AI follow your conventions in every session.

## Quick start

**Option 1: Use the general template (recommended)**

Copy `templates/AGENTS.md` into your project root and adjust:

```bash
curl -o AGENTS.md https://raw.githubusercontent.com/Mr404-404/ai-rules-cn/main/templates/AGENTS.md
```

**Option 2: Compose your own from rule modules**

Pick the modules you need from `rules/` and merge them into your project's `AGENTS.md` (or `CLAUDE.md` / `.cursorrules`):

```text
rules/
├── general/            # General rules
│   └── chinese-response.md       # Chinese responses & writing style
├── languages/          # Language conventions
│   ├── python.md                 # Python
│   └── javascript-typescript.md  # JavaScript / TypeScript
├── frameworks/         # Framework conventions
│   ├── react.md                  # React
│   └── vue.md                    # Vue
└── practices/          # Engineering practices
    ├── git-commit.md             # Commit messages
    ├── code-review.md            # AI code review checklist
    ├── security.md               # Security red lines
    ├── testing.md                # Testing conventions
    ├── sql-database.md           # SQL & database
    └── docker.md                 # Docker
```

**Option 3: Tool-specific templates**

`templates/` also ships `CLAUDE.md` and `.cursorrules` variants — copy into the project root.

## Writing principles

1. **Actionable**: every rule is a concrete behavior the AI can follow — no platitudes like "write good code"
2. **Boundaried**: telling the AI what NOT to do (no unsolicited refactors, no touching unrelated files) matters more than telling it what to do
3. **Minimal**: rules must stay within what an AI can reliably follow; each file stays under 80 lines

Note: the rule content is written in Chinese by design — it doubles as a prompt-level signal for the assistant to respond in Chinese. Contributions in Chinese are welcome; this English page is for discovery.

## License

[MIT](LICENSE) © Mr404-404
