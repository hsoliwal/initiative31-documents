# Initiative 31: a reader's map

**Could Eclipse SWT keep its API while reducing its dependence on three OS-specific implementations?** This repository records Initiative 31's investigation: what was tried, what was demonstrated, what was dropped, and what would still need to be built.

This is a research and documentation repository. You do not need a compiler, Java installation, or application server to read it. Its prototype implementations live in separate repositories linked by the original reports.

[Research cheat sheet](CHEATSHEET.md) · [Worked reading examples](READING_EXAMPLES.md) · [Original README](../README.md) · [Final report](../report/overall_report.md)

## Choose your first ten minutes

| Your question | Start here | What to look for |
| --- | --- | --- |
| What did the project conclude? | [Final report](../report/overall_report.md) | Executive summary, Results, and Conclusion |
| What would production work require? | [Realization Plan](../report/overall_report.md#realization-plan) | Capacity, steps, and the distinction between a demonstrator and a complete implementation |
| Why custom widgets with Skia? | [Skia results](../report/overall_report.md#skia-developed), then [custom-drawn assessment](../results/custom.md) | Benefits, limitations, dependencies, and remaining effort |
| Why were other paths dropped? | [GTK](../report/overall_report.md#gtk-dropped), [Swing](../report/overall_report.md#swing-dropped), and [Skia/VCL](../results/skia_vcl.md) | The project's reasons, rather than assumptions about general technology quality |
| How did the work evolve? | [Project phases](../report/overall_report.md#phases), then [meeting slides](../meetings/) | The date and scope of each observation |
| How do I check a claim? | [Evidence workflow](CHEATSHEET.md#claim-checking-workflow) | Exact revision, original section, and limits |

## The key ideas in plain language

| Term | Meaning in this collection |
| --- | --- |
| SWT | Eclipse's Standard Widget Toolkit and the API whose compatibility the project investigated |
| OS-agnostic implementation | The goal of sharing more implementation across operating systems, rather than maintaining independent widget implementations for each |
| Skia | A graphics/rendering library; drawing primitives are not a complete widget toolkit |
| Skija | Java bindings for Skia used in the custom-drawn approach described by the reports |
| VCL | LibreOffice's Visual Class Library, investigated as an existing widget framework; distinct from the later custom-widget approach |
| UNO | LibreOffice's component model and an investigated route to its controls |
| Demonstrator | An implementation used to establish feasibility; it is not a production-readiness or compatibility certification |
| Assessment | Recorded achievements, insights, risks, and conclusions for one technology at a particular stage |

The [final report](../report/overall_report.md) says the custom-widget/Skia demonstrator established feasibility and describes the work needed to complete it. Treat this as the project's documented conclusion, not as a promise that this repository contains an installable SWT replacement.

## Repository map

- [report/overall_report.md](../report/overall_report.md): the consolidated final narrative, rationale, results, and realization plan.
- [results/custom.md](../results/custom.md): custom-drawn widgets and Skia-based graphics, with limitations and screenshots.
- [results/skia_vcl.md](../results/skia_vcl.md): the earlier VCL/UNO investigation and its constraints.
- [results/gtk.md](../results/gtk.md) and [results/gtkCustomTheme.md](../results/gtkCustomTheme.md): GTK investigation and theming notes.
- [results/swing.md](../results/swing.md): Swing achievements, partial support, missing functionality, and assessment.
- [results/skia/results.md](../results/skia/results.md): additional Skia investigation notes.
- [results/_template.md](../results/_template.md): the existing structure for a technology assessment.
- [meetings/](../meetings/): dated presentations; these record the state at a meeting, not necessarily the final conclusion.
- [LICENSE](../LICENSE): the repository's retained Eclipse Public License 2.0 text.

## What this fork adds

The fork adds this reader map, a compact reference, and worked research/review examples. It does not change the original research, claim its authorship, introduce a new prototype, or turn an assessment into a support guarantee.

At the documentation baseline checked on 2026-10-14, both this fork's `main` and the public parent's `main` pointed to `46b66b41fbacc1ee3b5c420339267d588c16c7b9`. The underlying document collection was identical at that revision. See the [fork baseline](https://github.com/hsoliwal/initiative31-documents/tree/46b66b41fbacc1ee3b5c420339267d588c16c7b9) and [parent baseline](https://github.com/swt-initiative31/documents/tree/46b66b41fbacc1ee3b5c420339267d588c16c7b9). Later branch movement can change that comparison.

For current project context, use the [upstream organization](https://github.com/swt-initiative31) and the [published community profile](https://github.com/swt-initiative31/.github/blob/main/profile/README.md). This fork does not speak for the initiative or promise that historical communication channels are still active.

## A small, useful contribution

Pick one confusing claim or broken local link. Identify the exact document revision, quote only the necessary phrase, explain the ambiguity, and suggest a narrowly scoped correction with public evidence. Use the existing assessment template when proposing a comparable technology write-up. Keep historical findings intact unless you are explicitly correcting them, and label new observations with their own date and tested environment.

For changes to these added guides, target this fork. For original project findings, consult the public upstream repository and its current contribution arrangements. Do not treat a fork-specific edit as an accepted upstream conclusion.
