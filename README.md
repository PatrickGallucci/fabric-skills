# \# Copilot + Claude Skills for Microsoft Fabric

# 

# A curated set of \*\*agent skills\*\* designed for \*\*Microsoft Copilot\*\* and \*\*Claude\*\* workflows in \*\*Microsoft Fabric\*\*. These skills focus on \*\*performance diagnostics\*\*, \*\*remediation\*\*, \*\*security hardening\*\*, and \*\*operational monitoring\*\* across Fabric components (Lakehouse, OneLake, Notebooks, Spark, Data Factory, Power BI, REST APIs, RTI).

# 

# > \*\*Note\*\*: Skill behavior and tool permissions depend on your Copilot/Claude runtime and your Fabric tenant configuration. Review the \*\*Safety \& Permissions\*\* section before enabling write/remediation actions.

# 

# ---

# 

# \## Repository Structure

# 

# ```

# 

# .

# ├─ skills/

# │  ├─ fabric-data-agent/

# │  ├─ fabric-data-agent-perf-remediate/

# │  ├─ fabric-data-agent-remediate/

# │  ├─ fabric-data-factory-perf-remidiate/

# │  ├─ fabric-delta-spark-perf/

# │  ├─ fabric-iq/

# │  ├─ fabric-lakehouse-perf-remidiate/

# │  ├─ fabric-notebook-perf-remediate/

# │  ├─ fabric-onelake-perf-remediate/

# │  ├─ fabric-pbi-perf-remidiate/

# │  ├─ fabric-pbi-security-remediate/

# │  ├─ fabric-performance-monitoring/

# │  ├─ fabric-pyspark-perf-remediate/

# │  ├─ fabric-rest-api-perf-remediate/

# │  ├─ fabric-rest-api-remediate/

# │  ├─ fabric-rti-perf-remediate/

# │  ├─ fabric-spark-compute-perf-remediate/

# │  ├─ fabric-spark-compute-remediate/

# │  ├─ fabric-spark-perf-remediate/

# │  └─ fabric-udf-perf-remediate/

# ├─ fabric-data-agent.zip

# └─ README.md

# 

# ````

# 

# ---

# 

# \## Included Skills

# 

# | Skill | Purpose | Typical Output |

# |------|---------|----------------|

# | `fabric-data-agent` | General Fabric data agent helpers (triage, guidance, best practices) | diagnosis + suggested actions |

# | `fabric-data-agent-perf-remediate` | Performance triage + remediation for data workloads | prioritized fixes + expected impact |

# | `fabric-data-agent-remediate` | General remediation playbooks for data workloads | safe changes + rollback notes |

# | `fabric-data-agent.zip` | Packaged artifact for distribution/import | zip bundle |

# | `fabric-data-factory-perf-remidiate` | Data Factory pipeline performance remediation | pipeline tuning checklist + diffs |

# | `fabric-delta-spark-perf` | Delta + Spark performance optimization guidance | partition/Z-ORDER/file sizing guidance |

# | `fabric-iq` | Fabric “IQ” assistant skill (analysis, recommendations) | ranked insights + next steps |

# | `fabric-lakehouse-perf-remidiate` | Lakehouse performance remediation | layout/maintenance actions |

# | `fabric-notebook-perf-remediate` | Notebook performance remediation | code + config improvements |

# | `fabric-onelake-perf-remediate` | OneLake performance remediation | data organization + access guidance |

# | `fabric-pbi-perf-remidiate` | Power BI performance remediation | model/report tuning steps |

# | `fabric-pbi-security-remediate` | Power BI security remediation | RLS/OLS/permissions checklist |

# | `fabric-performance-monitoring` | Monitoring patterns (KPIs, alerts, runbooks) | dashboards + alert rules |

# | `fabric-pyspark-perf-remediate` | PySpark workload performance remediation | code patterns + execution tuning |

# | `fabric-rest-api-perf-remediate` | REST API performance remediation | batching/retry/backoff guidance |

# | `fabric-rest-api-remediate` | REST API remediation (correctness, failures) | fix steps + validation |

# | `fabric-rti-perf-remediate` | Real-time intelligence (RTI) perf remediation | throughput/latency tuning |

# | `fabric-spark-compute-perf-remediate` | Spark compute performance remediation | cluster sizing + job tuning |

# | `fabric-spark-compute-remediate` | Spark compute remediation (stability/correctness) | config fixes + guardrails |

# | `fabric-spark-perf-remediate` | Spark performance remediation (general) | execution plan improvements |

# | `fabric-udf-perf-remediate` | UDF performance remediation | rewrite patterns + alternatives |

# 

# > Spelling note: some skill folder names use `remidiate` vs `remediate`. The repo preserves the original names.

# 

# ---

# 

# \## Quick Start

# 

# \### 1) Clone

# ```bash

# git clone https://github.com/<your-org>/<your-repo>.git

# cd <your-repo>

# ````

# 

# \### 2) Use with Copilot / Claude

# 

# How you register skills depends on your host runtime. The typical flow is:

# 

# 1\. \*\*Import\*\* a skill folder from `skills/<skill-name>/`

# 2\. \*\*Configure tools\*\* (Fabric APIs, workspace access, GitHub permissions, etc.)

# 3\. \*\*Run\*\* the skill by name in your assistant environment

# 

# Example prompts:

# 

# \* “Run `fabric-spark-perf-remediate` on this Spark job output and propose safe changes.”

# \* “Use `fabric-pbi-security-remediate` to review this dataset + workspace access model.”

# 

# ---

# 

# \## Safety \& Permissions

# 

# Some skills are designed to produce \*\*remediation steps\*\* that may imply changes to:

# 

# \* Spark configs / cluster sizing

# \* Lakehouse layout and maintenance routines

# \* Data Factory pipeline settings

# \* Power BI model settings, RLS/OLS, tenant/workspace permissions

# \* REST API retry/batching behavior

# 

# \*\*Recommended operating mode\*\*

# 

# \* Default to \*\*read-only / advisory\*\* behavior

# \* Require explicit opt-in for any \*\*write\*\* actions

# \* Always include \*\*rollback\*\* instructions for remediations

# 

# \*\*Minimum controls\*\*

# 

# \* Least-privilege credentials (scope per workspace)

# \* Audit logging for tool calls and changes

# \* Change management gates for production environments

# 

# ---

# 

# \## Contributing

# 

# \### Adding a new skill

# 

# 1\. Create `skills/<new-skill-name>/`

# 2\. Include:

# 

# &nbsp;  \* `README.md` (skill intent, inputs/outputs, examples)

# &nbsp;  \* `skill.json` or equivalent manifest (depending on your runtime)

# &nbsp;  \* `tests/` with at least: golden-path, edge-case, adversarial prompt-injection case

# 3\. Update the root README “Included Skills” table.

# 

# \### Quality bar

# 

# \* Deterministic outputs where possible (schemas/templates)

# \* No unverified claims; cite authoritative sources when the skill references platform behavior

# \* Include validation steps and expected outcomes

# 

# ---

# 

# \## Versioning

# 

# \* Skills are versioned via Git tags and release notes.

# \* Any breaking change to inputs/outputs should bump a major version.

# \* Every bug fix must add a regression test.

# 

# ---

# 

# \## License

# 

# Add your license here (e.g., MIT, Apache-2.0, proprietary). If you include Microsoft or third-party trademarks/logos, ensure you follow their trademark guidelines.

# 

# ---

# 

# \## Support

# 

# \* Open an issue with:

# 

# &nbsp; \* Skill name

# &nbsp; \* Minimal reproduction prompt

# &nbsp; \* Sanitized logs/tool outputs

# &nbsp; \* Expected vs actual behavior

# 

# ```

# 

# If you want, I can also generate:

# \- a `CONTRIBUTING.md`

# \- a per-skill `README.md` template

# \- a simple `skills/<name>/skill.json` manifest skeleton (tell me your target runtime format).

# ::contentReference\[oaicite:0]{index=0}



