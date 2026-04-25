# Claude Code para Desenvolvimento Open Source

Material que eu uso nas minhas palestras e no meu fluxo de trabalho real com Claude Code para projetos open source.

**Rafael Zago** · Senior Software Automation Engineer · Red Hat

## O que tem aqui

- Apresentação em **PT-BR** e **EN** (33 slides cada)
- Tema terminal com paleta Catppuccin Macchiato
- Exemplos de AGENTS.md, Skills, Commands, PRD e Spec
- Fluxo completo: Spec Driven Dev → PRD → Plan → TDD → Review → MCP

## Ver online

**[claude.rafaelvzago.com](https://claude.rafaelvzago.com)**

## Rodar local

```bash
git clone git@github.com:rafaelvzago/claude-ai-slides.git
cd claude-ai-slides
python3 -m http.server 8080
# abrir http://localhost:8080
```

## Estrutura do repo

```
claude-ai-slides/
├── CLAUDE.md                    # convenções do projeto (agente lê automaticamente)
├── AGENTS.md                    # regras para agentes
├── CONTRIBUTING.md              # como contribuir
├── README.md                    # este arquivo
├── index.html                   # landing page
├── claude-code-open-source.html # slides PT-BR
├── claude-code-open-source-en.html # slides EN
├── docs/
│   └── architecture.md          # decisões técnicas
├── .claude/
│   ├── settings.json            # permissões e hooks
│   ├── commands/
│   │   └── review-slides.md     # command para revisar slides
│   └── skills/
│       ├── update-slides/
│       │   └── SKILL.md         # skill para atualizar slides
│       └── translate/
│           └── SKILL.md         # skill para traduzir slides
├── CNAME                        # GitHub Pages domain
└── LICENSE                      # Apache 2.0
```

Este repo é ao mesmo tempo a apresentação e um exemplo do que ela ensina.

## Licença

Apache 2.0
