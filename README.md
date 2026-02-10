# Copilot Claude Skills for Microsoft Fabric

A curated collection of AI Agent Skills that bring
Microsoft Fabric expertise directly into your development
workflow. Each skill teaches Claude structured
troubleshooting, performance remediation, and operational
guidance for specific Fabric workloads — so you spend less
time searching documentation and more time solving problems.

![Skills](https://img.shields.io/badge/skills-23-blue)
[![License](https://img.shields.io/badge/license-Apache%202.0-green)](LICENSE)

## How It Works

These skills follow the open
[Agent Skills specification](https://agentskills.io/) and
use a progressive-loading architecture. When you ask Claude
a question about Fabric, only the relevant skill loads into
context — keeping conversations fast and focused.

```text
You: "My MLV refresh keeps falling back to full."

Claude: [loads fabric-lakehouse-views-perf-remediate]
        -> Checks CDF status on source tables
        -> Reviews query for unsupported expressions
        -> Walks you through enabling optimal refresh
```

Each skill bundles:

- **SKILL.md** — main instructions with diagnostic
  checklists, step-by-step workflows, and troubleshooting
  matrices
- **references/** — deep-dive guides, failure-pattern
  catalogs, and architecture notes
- **scripts/** — ready-to-run SQL, PowerShell, or Python
  diagnostics
- **templates/** — fill-in-the-blank notebooks and runbooks

## Quick Start

### Install All Skills (User-Wide)

```bash
git clone https://github.com/<org>/copilot-claude-skills-fabric.git
cp -r copilot-claude-skills-fabric/skills/* \
      ~/.claude/skills/
```

### Install a Single Skill

```bash
cp -r \
  copilot-claude-skills-fabric/skills/fabric-lakehouse-perf-remediate \
  ~/.claude/skills/
```

### Install Into a Project

```bash
cp -r \
  copilot-claude-skills-fabric/skills/fabric-spark-perf-remediate \
  .claude/skills/
```

After copying, skills are available immediately. Claude
discovers them automatically based on your prompts — no
configuration required.

## Skills Catalog

The repository contains **23 skills** organized across nine
Fabric workload areas.

### Data Agent

Configure, troubleshoot, and optimize Fabric Data Agent
capabilities.

| Skill | Purpose |
|---|---|
| [fabric-data-agent][s01] | Core Data Agent configuration, setup, and operational workflows |
| [fabric-data-agent-perf-remediate][s02] | Response latency, throughput optimization, and performance diagnostics |
| [fabric-data-agent-remediate][s03] | Error resolution, connectivity failures, and configuration fixes |

[s01]: skills/fabric-data-agent/
[s02]: skills/fabric-data-agent-perf-remediate/
[s03]: skills/fabric-data-agent-remediate/

### Data Factory

Pipeline performance and remediation for Fabric Data
Factory.

| Skill | Purpose |
|---|---|
| [fabric-data-factory-perf-remediate][s04] | Pipeline tuning, activity duration, copy-activity diagnostics |

[s04]: skills/fabric-data-factory-perf-remediate/

### Lakehouse

Lakehouse access control, materialized views, and query
optimization.

| Skill | Purpose |
|---|---|
| [fabric-lakehouse-access-control][s05] | OneLake RBAC, workspace roles, table-level security, sharing |
| [fabric-lakehouse-perf-remediate][s06] | Query performance, table maintenance, V-Order, bin-compaction |
| [fabric-lakehouse-views-perf-remediate][s07] | MLV refresh optimization, incremental refresh, CDF, lineage |

[s05]: skills/fabric-lakehouse-access-control/
[s06]: skills/fabric-lakehouse-perf-remediate/
[s07]: skills/fabric-lakehouse-views-perf-remediate/

### Spark and Compute

Apache Spark workloads, compute configuration, PySpark
optimization, and UDF tuning.

| Skill | Purpose |
|---|---|
| [fabric-delta-spark-perf][s08] | Delta Lake on Spark: file sizing, Z-order, partition pruning, caching |
| [fabric-spark-compute-perf-remediate][s09] | Pool sizing, autoscale configuration, resource allocation |
| [fabric-spark-compute-remediate][s10] | Compute error resolution, pool failures, session management |
| [fabric-spark-perf-remediate][s11] | Shuffle tuning, join strategies, broadcast thresholds |
| [fabric-pyspark-perf-remediate][s12] | Pandas UDFs, Arrow integration, Python worker tuning |
| [fabric-udf-perf-remediate][s13] | Serialization overhead, vectorized UDFs, SQL alternatives |

[s08]: skills/fabric-delta-spark-perf/
[s09]: skills/fabric-spark-compute-perf-remediate/
[s10]: skills/fabric-spark-compute-remediate/
[s11]: skills/fabric-spark-perf-remediate/
[s12]: skills/fabric-pyspark-perf-remediate/
[s13]: skills/fabric-udf-perf-remediate/

### Notebook

Fabric notebook execution and performance.

| Skill | Purpose |
|---|---|
| [fabric-notebook-perf-remediate][s14] | Session startup, cell latency, environment config, libraries |

[s14]: skills/fabric-notebook-perf-remediate/

### OneLake

OneLake storage-layer performance.

| Skill | Purpose |
|---|---|
| [fabric-onelake-perf-remediate][s15] | I/O throughput, shortcuts, cross-region latency, tiering |

[s15]: skills/fabric-onelake-perf-remediate/

### Power BI

Semantic model performance and security.

| Skill | Purpose |
|---|---|
| [fabric-pbi-perf-remediate][s16] | DAX optimization, model refresh, Direct Lake, rendering |
| [fabric-pbi-security-remediate][s17] | RLS, OLS, workspace access, sensitivity labels |

[s16]: skills/fabric-pbi-perf-remediate/
[s17]: skills/fabric-pbi-security-remediate/

### REST API

Fabric REST API integration and performance.

| Skill | Purpose |
|---|---|
| [fabric-rest-api-perf-remediate][s18] | Latency, throttling, batch ops, long-running op polling |
| [fabric-rest-api-remediate][s19] | Auth failures, payload issues, error resolution |

[s18]: skills/fabric-rest-api-perf-remediate/
[s19]: skills/fabric-rest-api-remediate/

### Real-Time Intelligence

Fabric Real-Time Intelligence workloads.

| Skill | Purpose |
|---|---|
| [fabric-rti-perf-remediate][s20] | Eventhouse ingestion, KQL performance, RT dashboards |

[s20]: skills/fabric-rti-perf-remediate/

### Network and Security

Network connectivity and security configuration.

| Skill | Purpose |
|---|---|
| [fabric-network-remediate][s21] | Private endpoints, managed VNet, firewall, outbound access |

[s21]: skills/fabric-network-remediate/

### Platform Monitoring

Cross-cutting performance monitoring and intelligent
diagnostics.

| Skill | Purpose |
|---|---|
| [fabric-performance-monitoring][s22] | Capacity metrics, throttling, CU consumption, workload mgmt |
| [fabric-iq][s23] | Fabric Copilot/IQ, natural-language diagnostics, insights |

[s22]: skills/fabric-performance-monitoring/
[s23]: skills/fabric-iq/

## Repository Structure

```text
copilot-claude-skills-fabric/
├── README.md
├── LICENSE
├── CONTRIBUTING.md
├── CHANGELOG.md
└── skills/
    ├── fabric-data-agent/
    │   ├── SKILL.md
    │   ├── LICENSE.txt
    │   ├── references/
    │   ├── scripts/
    │   └── templates/
    ├── fabric-data-agent-perf-remediate/
    │   └── ...
    └── ... (23 skill directories)
```

Each skill is self-contained. Install individual skills or
the entire collection.

## Skill Anatomy

Every skill follows the same internal structure:

```text
fabric-<workload>-<category>/
├── SKILL.md           <- Entry point (< 500 lines)
├── LICENSE.txt        <- Apache 2.0
├── references/        <- Deep-dive docs (on demand)
│   ├── common-failures.md
│   └── architecture.md
├── scripts/           <- Diagnostic scripts
│   ├── health-check.sql
│   └── audit.ps1
└── templates/         <- Notebook/runbook starters
    └── diagnostic.sql
```

**Progressive loading** means Claude reads only the `name`
and `description` from YAML frontmatter during discovery.
The full SKILL.md body loads when your prompt matches.
Scripts, references, and templates load only when Claude
needs them during a workflow.

## Naming Conventions

Skills follow a consistent naming pattern:

```text
fabric-{workload}-{category}
```

| Segment | Example Values | Meaning |
|---|---|---|
| `fabric` | — | All skills target Fabric |
| workload | `lakehouse`, `spark`, `pbi` | Fabric service area |
| category | `perf-remediate`, `remediate` | Type of guidance |

**Category definitions:**

- **perf-remediate** — Performance diagnosis and
  optimization
- **remediate** — Error resolution and functional fixes
- **access-control** — Security, RBAC, and permissions
- **perf** — Performance best practices and patterns
  (no active remediation)

## Requirements

- **Claude Desktop**, **Claude Code**, **VS Code with
  Copilot**, or any tool supporting the
  [Agent Skills spec](https://agentskills.io/)
- **Microsoft Fabric** workspace (any SKU) for running
  diagnostic scripts
- **Fabric Notebook** or **SQL analytics endpoint** for
  executing bundled SQL scripts

No API keys or additional dependencies are required. The
bundled scripts are standard Spark SQL, T-SQL, and
PowerShell.

## Contributing

Contributions are welcome. See
[CONTRIBUTING.md](CONTRIBUTING.md) for guidelines on adding
new skills, updating existing content, reporting
inaccuracies, and submitting diagnostic scripts.

All skills must pass the validation checklist before merge:

- [ ] Valid YAML frontmatter (`name` and `description`)
- [ ] `name` is lowercase with hyphens (max 64 chars)
- [ ] `description` states WHAT, WHEN, and keywords
  (max 1024 chars)
- [ ] SKILL.md body under 500 lines
- [ ] Large workflows split into `references/`
- [ ] Scripts include usage comments and error handling
- [ ] All resource paths are relative
- [ ] No hardcoded credentials or secrets
- [ ] Apache 2.0 `LICENSE.txt` included

## License

This project is licensed under the Apache License 2.0.
See [LICENSE](LICENSE) for the full text.

Microsoft Fabric, Power BI, OneLake, and related product
names are trademarks of Microsoft Corporation. This project
is not affiliated with or endorsed by Microsoft.

## Acknowledgments

Built with information from
[Microsoft Learn](https://learn.microsoft.com/fabric/) and
real-world Fabric operational experience. Skills follow the
[Agent Skills specification](https://agentskills.io/).