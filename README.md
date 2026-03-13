# Aegro Skills — Claude Code Plugin

12 AI skills for agricultural management with [Aegro](https://aegro.com.br). Turns Claude into an agronomic assistant that can query farm data, analyze profitability, reconcile stock, close crop seasons, and more.

[![Plugin](https://img.shields.io/badge/Claude_Code-plugin-blue)](https://claude.ai)
[![Skills](https://img.shields.io/badge/skills-12-green)]()
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

---

## Install

### Via Claude Code plugin (recommended)

```
/plugin marketplace add pmdusso/aegro-skills
/plugin install aegro-skills@pmdusso-aegro-skills
```

### Via Aegro CLI

```bash
pip install aegro       # or: uv tool install aegro
aegro skills install    # copies skills to ~/.claude/skills/
```

---

## Skills

### Domain skills (personas)

These skills give Claude deep knowledge of a specific Aegro domain. Claude loads them automatically when your conversation matches the domain.

| Skill | What it knows |
|-------|---------------|
| **aegro-agronomo** | Crops, fields, activities, harvests, weather, production inputs |
| **aegro-estoquista** | Stock items, storage locations, movements, catalogs, elements |
| **aegro-financeiro** | Bills, installments, categories, bank accounts, companies |
| **aegro-operacional** | Farms, authentication, tags, cross-domain orchestration |
| **aegro-patrimonial** | Machines, vehicles, fuel supplies, maintenance records |

### Workflow skills

These are guided step-by-step workflows. Invoke them directly or let Claude trigger them when relevant.

| Skill | What it does |
|-------|-------------|
| **aegro-visao-geral** | Quick farm overview — active crops, financial position, pending bills, stock alerts |
| **aegro-fechamento-safra** | Guided crop season closing checklist with data validation |
| **aegro-lancamento-financeiro** | Step-by-step guide to create accounts payable and receivable |
| **aegro-reconciliacao-estoque** | Identify discrepancies between physical stock, activities, and financials |
| **aegro-monitoramento-pragas** | Track pesticide applications, consumption, and efficacy |
| **aegro-analise-rentabilidade** | Calculate ROI, cost per hectare, and gross margin per crop |
| **aegro-cadastro-patrimonio** | Register and manage assets, fuel supplies, and maintenance |

---

## How it works

```
You: "Como esta a Fazenda Norte?"

Claude: [loads aegro-visao-geral]
  → aegro crops list
  → aegro financial installments --status PENDING
  → aegro stock items

Claude: "A Fazenda Norte tem 3 safras ativas. Soja 24/25 com custo de
R$2.400/ha e margem de 35%. Há 4 parcelas pendentes totalizando R$52k
com vencimento esta semana. Estoque de glifosato abaixo do mínimo..."
```

The skills guide Claude to:
1. Call the right `aegro` CLI commands
2. Interpret the agronomic data correctly
3. Present actionable insights in context

---

## Requirements

- [Claude Code](https://claude.ai/download) v1.0.33+
- [Aegro CLI](https://pypi.org/project/aegro/) installed and authenticated (`aegro auth login`)
- Active Aegro subscription with API access

## Quick start

```bash
# 1. Install the CLI
pip install aegro

# 2. Authenticate
aegro auth login --api-key "aegro_your_key_here"

# 3. Install the plugin in Claude Code
# Then in Claude Code:
/plugin marketplace add pmdusso/aegro-skills
/plugin install aegro-skills@pmdusso-aegro-skills

# 4. Start asking
# "Qual o panorama da fazenda?"
# "Feche a safra de soja 24/25"
# "Quanto gastei de defensivo no milho?"
```

---

## About Aegro

[Aegro](https://aegro.com.br) is a farm management platform used by thousands of farms in Brazil. It covers crop planning, financial management, stock control, asset tracking, and more.

This plugin is maintained by [Aegro Engineering](https://github.com/aegro).

## License

[MIT](LICENSE)
