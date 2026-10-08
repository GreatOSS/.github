# Experiment summary

## Question and task

The experiment asks whether an autonomous coding agent can turn a broad product mission into a useful PDF application, then improve it through research, implementation, tests, and direct use of its interface.

The shared [mission](../examples/mission.txt) asks the maintainer to:

- Research and choose a distinct product name.
- Build and maintain the assigned GitHub project, including reviewing issues and pull requests.
- Investigate user wishes and competing software.
- Prioritize usability, functionality, correctness, compatibility, performance, and appearance.
- Exercise the actual application with browser and desktop tools, record what was tested, and fix observed rough edges.
- Make routine maintenance decisions autonomously.

The owner supplied the mission and infrastructure. The agents chose their product names, product scope, code, tests, and maintenance priorities. The repository URL was substituted for each deployment; the canonical mission was not rewritten to give different product objectives to different models.

## Cohorts and timeline

### Earlier exploratory deployments

The setup evolved through single-VM and subscription-backed trials, repository renames, mail integration, browser tooling, and dashboards. Two surviving predecessor repositories are now published:

| Repository | Product | Status |
|---|---|---|
| [pdf-gemini-deprec](https://github.com/GreatOSS/pdf-gemini-deprec) | ZephyrPDF | Deprecated predecessor; [website](https://greatoss.github.io/pdf-gemini-deprec/) |
| [pdf-astra-deprec](https://github.com/GreatOSS/pdf-astra-deprec) | FolioVale | Deprecated predecessor; [website](https://greatoss.github.io/pdf-astra-deprec/) |

Their histories were not imported into the final clean sessions. Their earlier usage is excluded from the final budgets below. This report does not claim an equivalent historical spend reconstruction for these predecessors.

### Clean restart: 29 September 2026

Before the final restart, a trace audit found setup contamination: operational instructions mentioned earlier implementations and other agents, shared installation paths named a particular model, and monitor source/footer text mentioned other deployments. Initial runs had also encountered insufficient GitHub write permissions. One run changed its repository to public, and others published Pages sites, weakening the intended source isolation.

The owner requested a full reset. All four model processes were stopped. Agent homes and history were archived outside the agent accounts' access. New workspaces, conversations, memories, browser state, inboxes, mail delivery records, and usage ledgers were created. Repositories were reset to a single empty initialization commit, with old reachable branches/tags, releases, Actions runs/artifacts, and deployments removed. All repositories were private and Pages was disabled during the clean runs.

The setup renamed the common tool directory to `/opt/agent-tools`, removed cross-model monitor references, and audited injected operational instructions and MCP tool descriptions. No references to other model deployments, former product names, or earlier conversations were found in that audit. This is a bounded audit result, not a claim that all possible indirect clues or GitHub-retained unreachable objects were erased.

Fresh sessions began around **2026-09-29 11:24 UTC**. Spending and token counters started at zero. Each deployment had its own $100 allowance.

### Changes during the clean runs

The infrastructure was still evolving:

- The ordinary cooldown changed from **30 minutes to 5 minutes** on 29 September. Configuration was applied between turns, preserving sessions and in-progress work. Mail could already wake agents sooner.
- A restricted package-install helper was added so agents could install Ubuntu packages without general root access or VM shutdown authority.
- Private local previews were added, built from workspace snapshots and exposed through the dashboard's SSH-protected interface.
- Opus encountered a browser evaluation blocked by an unsaved-changes dialog. Claude's 30-minute idle timeout eventually returned an error and the agent continued autonomously. An attempted external dialog interaction did not execute because the desktop-control executable was absent; a package installation completed, but the dialog was not manually cleared and the session was not restarted for that incident.

These interventions are part of the experiment's conditions. They prevent describing it as a fully fixed, intervention-free benchmark.

### Stop and publication

All four runs reached their independent budget limits on 29–30 September and were permanently stopped by the host watchdog. On **8 October 2026**, the owner authorized public repositories and GitHub Pages.

Publication was performed by the operator, not by additional model turns. It added deployment workflows, README links, and deployment-base asset fixes where necessary. Those publication commits should not be counted as agent-generated implementation work. Uncommitted changes left in the Opus and Astra workspaces were preserved rather than silently included in the published applications. The deprecated repositories were subsequently published as historical artifacts, with separate website URLs and deprecation labels.

## Final clean-run measurements

Source: the per-VM usage ledgers and durable host budget-stop records, exported on **8 October 2026**. [Machine-readable data](../data/2026-09-29-clean-runs.json) contains exact recorded totals, token categories, and timestamps. Times below are UTC.

| Deployment | Estimated USD at stop | Elapsed hours¹ | Cycles dispatched² | Usage records³ | Budget stop |
|---|---:|---:|---:|---:|---|
| Gemini / FolioFlux | $100.063626 | 22.1742 | 187 | 3,305 | Sep 30, 09:35:19 |
| Opus / Leaflark | $100.040251 | 29.6583 | 225 | 1,786 | Sep 30, 17:04:21 |
| Fable / Leafline | $100.026298 | 16.0487 | 115 | 1,033 | Sep 30, 03:27:47 |
| Astra / Leafrune | $100.732674 | 1.5283 | 3 | 142 | Sep 29, 12:56:37 |

1. From the first recorded usage event to the host budget stop; includes waits, tool execution, cooldowns, and interruptions. This is not model inference time.
2. Runner mission submissions, not completed features, commits, or an equal amount of work. A cycle may contain many model/tool exchanges or end in an interruption.
3. Deduplicated ledger entries, not guaranteed to equal underlying HTTP requests, successful tasks, or human-visible answers.

| Deployment | Uncached input | Output as recorded | Cache reads | Cache writes |
|---|---:|---:|---:|---:|
| Gemini | 29,895,132 | 710,111 | 999,724,805 | 0 |
| Opus | 3,572 | 71,258 | 409,553,893 | 2,086,253 (1-hour) |
| Fable | 29,606 | 49,499 | 249,606,353 | 1,742,685 (1-hour) |
| Astra | 9,493,459 | 48,946 | 3,350,784 | 0 |

These categories are accumulated provider/runtime usage reports. Cached token counts include repeated reads of the same context and are **not unique text processed**. Claude cache-creation tokens are separate from its uncached-input count. Output treatment differs by adapter; see [accounting](setup.md#cost-accounting-and-the-stop-rule). Raw totals should not be treated as interchangeable measures of intelligence or productivity across providers. All four final mail counters were zero; this run's measurements do not establish comparative performance at handling mail.

The small overshoots reflect in-flight requests and reporting/polling delay. These are token-price estimates, **not actual subscription invoices or a guarantee of exact cash spend**.

## What was produced

| Deployment | Product | Published source | Last committed agent revision before publication work |
|---|---|---|---|
| Gemini | FolioFlux | [pdf-gemini](https://github.com/GreatOSS/pdf-gemini) | [76d3d07](https://github.com/GreatOSS/pdf-gemini/tree/76d3d07) |
| Opus | Leaflark | [pdf-opus](https://github.com/GreatOSS/pdf-opus) | [df92141](https://github.com/GreatOSS/pdf-opus/tree/df92141) |
| Fable | Leafline | [pdf-fable](https://github.com/GreatOSS/pdf-fable) | [4010e80](https://github.com/GreatOSS/pdf-fable/tree/4010e80) |
| Astra | Leafrune | [pdf-astra](https://github.com/GreatOSS/pdf-astra) | [714e54a](https://github.com/GreatOSS/pdf-astra/tree/714e54a) |

All four converged on browser applications using Vite and PDF.js; PDF manipulation also uses pdf-lib or a related fork. The repositories contain differing readers, annotation tools, page operations, export behavior, and additional features. The repository READMEs describe their intended capabilities; those descriptions are agent-authored claims unless independently verified.

Publication validation included dependency installation, repository tests and production builds, then opening each live site in Chromium and loading/rendering a small PDF. The sites are available from the [project index](../README.md). This does not establish a winner, validate every advertised feature, or certify difficult cases such as secure redaction, existing-text editing, signatures, accessibility, or malformed documents.

## Interpretation and limitations

- **One final run per model:** no repeated trials, confidence intervals, or blinded human UX scoring.
- **Different harnesses:** Gemini/Astra used OpenCode; Opus/Fable used Claude Code. Tool behavior, prompts, compaction, retry policy, and accounting differ.
- **Different pricing:** equal estimated-dollar allowances buy very different token quantities and elapsed time. Astra's shorter run is not, by itself, a quality result.
- **Different authentication arrangements:** Gemini used an API key, Claude models used subscription OAuth, and Astra used a host-side subscription gateway. Subscription availability and shared account usage can affect throughput.
- **Changing infrastructure:** cooldowns, package installation, and previews changed during the run; early setup faults were corrected before the clean restart.
- **Isolation has limits:** separate VMs, private repositories, scoped tokens and firewall rules reduce direct sharing, but public internet research and common dependencies remain shared inputs. After publication, source privacy no longer provides isolation.
- **Approximate measurement:** recorded-token pricing was not reconciled to provider invoices. Auxiliary requests, retries, cache reporting, and runtime-specific usage semantics affect comparisons.
- **Operator publication work:** Pages workflows and hosting fixes are explicitly separated from the frozen agent revisions.

A stronger follow-up would freeze the harness and prompts, use repeated seeded runs, keep identical intervention rules and tool limits, archive comparable usage events, and score the apps against a predefined PDF corpus and blinded usability tasks.
