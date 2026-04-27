# Claude Code for Open Source Development

Material I use in my talks and in my actual day-to-day workflow with Claude Code for open source projects.

**Rafael Zago** · Senior Software Automation Engineer · Red Hat

## What's inside

- Presentation in **PT-BR** and **EN** (33 slides each)
- Terminal theme with the Catppuccin Macchiato palette
- Examples of AGENTS.md, Skills, Commands, PRD and Spec
- Full workflow: Spec Driven Dev → PRD → Plan → TDD → Review → MCP

## View online

**[claude.rafaelvzago.com](https://claude.rafaelvzago.com)**

## Run locally

```bash
git clone git@github.com:rafaelvzago/claude-ai-slides.git
cd claude-ai-slides
python3 -m http.server 8080
# open http://localhost:8080
```

## Repository structure

```
claude-ai-slides/
├── CLAUDE.md                       # project conventions (auto-read by agent)
├── AGENTS.md                       # agent rules
├── CONTRIBUTING.md                  # how to contribute
├── README.md                       # this file
├── index.html                      # landing page
├── claude-code-open-source.html    # slides PT-BR
├── claude-code-open-source-en.html # slides EN
├── docs/
│   ├── architecture.md             # technical decisions
│   └── PRD.md                      # product requirements document
├── .claude/
│   ├── settings.json               # permissions and hooks
│   ├── commands/
│   │   ├── commit.md               # /commit — conventional commit workflow
│   │   ├── fix-accentuation.md     # /fix-accentuation — fix PT-BR accents
│   │   ├── review-slides.md        # /review-slides — review slide integrity
│   │   └── update-readme.md        # /update-readme — sync README structure tree
│   └── skills/
│       ├── commit/
│       │   └── SKILL.md            # conventional commits with pre-commit checks
│       ├── fix-accentuation/
│       │   └── SKILL.md            # correct PT-BR accentuation in slides
│       ├── update-readme/
│       │   └── SKILL.md            # sync README tree with filesystem
│       ├── update-slides/
│       │   └── SKILL.md            # add, remove, or reorder slides
│       └── translate/
│           └── SKILL.md            # sync translations between PT-BR and EN
├── CNAME                           # GitHub Pages domain
└── LICENSE                         # Apache 2.0
```

This repo is both the presentation and an example of what it teaches.

## License

Apache 2.0
