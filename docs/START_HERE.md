# Initiative 31: a reader's map

**Could Eclipse SWT keep its API while reducing its dependence on three OS-specific implementations?** This repository records Initiative 31's investigation: what was tried, what was demonstrated, what was dropped, and what would still need to be built.

This is a research and documentation repository. You do not need a compiler, Java installation, or application server to read it. Its prototype implementations live in separate repositories linked by the original reports.

[Research cheat sheet](CHEATSHEET.md) · [Worked reading examples](READING_EXAMPLES.md) · [Original README](../README.md) · [Final report](../report/overall_report.md)

[Complete collection map](CONTENT_MAP.md) · [Evidence and review](EVIDENCE_AND_REVIEW.md)

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
- [results/skia/results.md](../results/skia/results.md): early LibreOffice VCL/UNO design notes, including proposed single-process integration; distinct from the later custom-widget demonstrator.
- [results/_template.md](../results/_template.md): the existing structure for a technology assessment.
- [meetings/](../meetings/): dated presentations; these record the state at a meeting, not necessarily the final conclusion.
- [LICENSE](../LICENSE): the repository's retained Eclipse Public License 2.0 text.

## From a report to the right implementation

Repository names alone can be misleading: the early VCL route and the final custom-widget demonstrator are separate experiments. Use the report section first, then the implementation's own instructions.

| Investigation | Public implementation entry point | Evidence in this collection |
| --- | --- | --- |
| Final custom-widget/Skia demonstrator | [`prototype-skija`](https://github.com/swt-initiative31/prototype-skija), including its setup and state notes | [Skia: Developed](../report/overall_report.md#skia-developed) and [custom-drawn assessment](../results/custom.md) |
| Skia drawing on a canvas with existing SWT | [`skija-canvas`](https://github.com/swt-initiative31/skija-canvas) | [Skia-based GC in SWT](../report/overall_report.md#skia-based-gc-in-swt) |
| Earlier SWT-to-VCL experiment | [`prototype-skiavcl`](https://github.com/swt-initiative31/prototype-skiavcl) | [VCL and UNO achievements](../results/skia_vcl.md#achievements) |
| LibreOffice-side VCL extraction | [`prototype-skiavcl-libreoffice`](https://github.com/swt-initiative31/prototype-skiavcl-libreoffice), with the historical `vcl-4-swt` experiment | [Tight Integration of VCL into LibreOffice](../results/skia_vcl.md#tight-integration-of-vcl-into-libreoffice) |
| GTK across operating systems | [`prototype-gtk`](https://github.com/swt-initiative31/prototype-gtk) | [GTK: Dropped](../report/overall_report.md#gtk-dropped) and [GTK assessment](../results/gtk.md) |
| SWT implemented through Swing | [`prototype-swing`](https://github.com/swt-initiative31/prototype-swing) | [Swing: Dropped](../report/overall_report.md#swing-dropped) and [Swing assessment](../results/swing.md) |

These are upstream research repositories, not installation instructions for this document collection. The two VCL repositories were archived at the 2026-10-14 source check. Older assessment links use names such as `prototype-skia` and `prototype-skia-libreoffice`; retain those historical citations when discussing the original evidence, and use the canonical repository names above for navigation. Check the chosen repository's branch and revision before reproducing an experiment.

## What remains before production

The final report's [Content / Steps](../report/overall_report.md#content--steps) identifies five concrete areas. This index makes the distinction between the demonstrated result and proposed production work explicit:

- **Event handling:** replace more OS-provided keyboard, mouse, focus, and selection behavior
- **One canvas:** replace the native backing widget for each custom widget with a shared native canvas, including refresh-area calculations
- **Full GC:** complete drawing API functionality beyond the subset needed by the demonstrator
- **Performance:** address the extra rendering-buffer copy and validate platform-specific rendering paths
- **Widget finalization:** complete relevant capabilities beyond preliminary widget implementations

These are the report's proposed steps, not a newly approved roadmap. Its [Capacity / Effort](../report/overall_report.md#capacity--effort) estimate belongs to that scope and those assumptions; it is not a current delivery promise.

## What this fork adds

The fork adds this reader map, a compact reference, and worked research/review examples. It does not change the original research, claim its authorship, introduce a new prototype, or turn an assessment into a support guarantee.

At the documentation baseline checked on 2026-10-14, both this fork's `main` and the public parent's `main` pointed to `46b66b41fbacc1ee3b5c420339267d588c16c7b9`. The underlying document collection was identical at that revision. See the [fork baseline](https://github.com/hsoliwal/initiative31-documents/tree/46b66b41fbacc1ee3b5c420339267d588c16c7b9) and [parent baseline](https://github.com/swt-initiative31/documents/tree/46b66b41fbacc1ee3b5c420339267d588c16c7b9). Later branch movement can change that comparison.

For current project context, use the [upstream organization](https://github.com/swt-initiative31) and the [published community profile](https://github.com/swt-initiative31/.github/blob/main/profile/README.md). This fork does not speak for the initiative or promise that historical communication channels are still active.

## A small, useful contribution

Pick one confusing claim or broken local link. Identify the exact document revision, quote only the necessary phrase, explain the ambiguity, and suggest a narrowly scoped correction with public evidence. Use the existing assessment template when proposing a comparable technology write-up. Keep historical findings intact unless you are explicitly correcting them, and label new observations with their own date and tested environment.

For changes to these added guides, target this fork. For original project findings, consult the public upstream repository and its current contribution arrangements. Do not treat a fork-specific edit as an accepted upstream conclusion.
