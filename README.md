# GreatOSS: autonomous PDF maintainer experiments

What happens when coding agents are asked to create and maintain a useful open-source PDF application, given a Linux VM, browser and desktop tools, repository access, and a finite budget?

This organization records that experiment. The mission prioritizes a polished user experience, hands-on testing, compatibility, performance, and maintainership. The agents choose their own product names and implementation approaches.

## Final clean experiments

These four deployments started from clean state on **29 September 2026**. Each received its own **$100 API-equivalent usage allowance** and stopped when the host monitor reached that threshold. Their repositories and websites were published on **8 October 2026**.

| Configured model | Product / source | Website |
|---|---|---|
| Gemini 3.8 Flash | [FolioFlux](https://github.com/GreatOSS/pdf-gemini) | [Open app](https://greatoss.github.io/pdf-gemini/) |
| Opus 5.5, medium effort | [Leaflark](https://github.com/GreatOSS/pdf-opus) | [Open app](https://greatoss.github.io/pdf-opus/) |
| Fable 5.1, medium effort | [Leafline](https://github.com/GreatOSS/pdf-fable) | [Open app](https://greatoss.github.io/pdf-fable/) |
| GPT-6 Astra, medium effort | [Leafrune](https://github.com/GreatOSS/pdf-astra) | [Open app](https://greatoss.github.io/pdf-astra/) |

The model names are the configured identifiers in this deployment. Runtime behavior, pricing coefficients, and measurements are documented below; this is an exploratory engineering comparison, not a controlled benchmark or a quality ranking.

## Deprecated predecessors

These preserve earlier experiments. They are **not part of the clean $100-per-deployment comparison**.

| Earlier experiment | Source | Website |
|---|---|---|
| Gemini / ZephyrPDF | [pdf-gemini-deprec](https://github.com/GreatOSS/pdf-gemini-deprec) | [Open deprecated app](https://greatoss.github.io/pdf-gemini-deprec/) |
| Astra / FolioVale | [pdf-astra-deprec](https://github.com/GreatOSS/pdf-astra-deprec) | [Open deprecated app](https://greatoss.github.io/pdf-astra-deprec/) |

## Documentation

- [Experiment summary, results, timeline, and limitations](docs/experiments.md)
- [Detailed infrastructure and agent setup](docs/setup.md)
- [Shared mission template](examples/mission.txt)
- [Sanitized final measurements](data/2026-09-29-clean-runs.json)

All six sites are browser applications. The publication checks establish that each site loads and can render a sample PDF; they are not a comprehensive correctness, accessibility, privacy, or security certification. Consult each project's documentation before relying on a feature such as redaction, signatures, OCR, or form preservation.

This repository contains documentation and sanitized measurements. It does not contain account credentials, private agent conversations, mailbox contents, VM disk images, or a turnkey infrastructure installer.
