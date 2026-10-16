# Document collection and coverage map

[Home](../README.md) · [Reader guide](START_HERE.md) · [Evidence and review](EVIDENCE_AND_REVIEW.md)

## Repository boundary

This is the public fork of [swt-initiative31/documents](https://github.com/swt-initiative31/documents). It preserves the initiative's research record and adds reader guidance. The report explains the initiative's evaluation of an OS-agnostic SWT implementation; the implementation itself is maintained in separate repositories.

The inventory below describes the complete tracked tree at [commit `1a5720a`](https://github.com/hsoliwal/initiative31-documents/tree/1a5720a31a1b423548eee3c9a5bb3bfcdbac17fd), inspected on 2026-10-14, before this map and its companion review guide were added. It contains 85 files: 12 Markdown documents, 63 PNG images, eight PowerPoint presentations, one PDF, and one license. All 11 tracked directories are accounted for below. No program source files, build manifests, executable test suites, workflow definitions, submodules, `AGENTS.md`, or `CONTRIBUTING` files appear in that tree.

Consequently, `report`, `results`, and `meetings` are **document groups**, not software modules. Java packages, public API signatures, runtime configuration, and build/test commands belong to the linked implementation repositories. Their names or code excerpts inside a report do not create packages in this repository.

## Reading and dependency direction

1. The [root README](../README.md) identifies the research and its final outcome.
2. The reader guides help locate evidence; they do not replace it.
3. The [final report](../report/overall_report.md) consolidates the project's goals, technology choices, results, and proposed realization plan.
4. Individual assessments retain their own phase-specific observations, limitations, and contributor credits.
5. Images and presentations support the record. Prototype code is reached through the report and assessment links, then reviewed at its own revision.

These are reading relationships, not build dependencies. The final report provides the consolidated conclusion, but does not automatically supersede every technical detail in an earlier assessment. Compare the technology, phase, and scope of each claim.

## Every Markdown document in the inspected snapshot

| Document | Purpose and reading boundary |
| --- | --- |
| [README.md](../README.md) | Entry point, final-report link, and technology assessment index; retains the upstream introduction |
| [docs/START_HERE.md](START_HERE.md) | Reader routes, vocabulary, implementation repository map, and remaining production-work index |
| [docs/CHEATSHEET.md](CHEATSHEET.md) | Document-inspection commands, claim-checking workflow, review checklist, and navigation troubleshooting |
| [docs/READING_EXAMPLES.md](READING_EXAMPLES.md) | Worked examples for comparing reports, preparing a brief, and citing an exact revision; not executable SWT examples |
| [report/overall_report.md](../report/overall_report.md) | Final synthesis: goal, setup, phases, candidate selection, outcomes, follow-up opportunities, effort assumptions, and realization steps |
| [results/_template.md](../results/_template.md) | Unfilled assessment structure: Technology, Contributors, Results, Conclusion, and Appendix; placeholders are not findings |
| [results/custom.md](../results/custom.md) | Earlier custom-drawn widget assessment: partial widgets, interchangeable rendering, native superclass/GC dependencies, quality/performance risks, and screenshots; its work-in-progress conclusion is distinct from the final report |
| [results/gtk.md](../results/gtk.md) | GTK evaluation, especially Windows integration: multiple displays, AWT embedding, browser/printing limitations, reported timings, and intermediate assessment |
| [results/gtkCustomTheme.md](../results/gtkCustomTheme.md) | GTK theme-configuration walkthrough with Linux/Windows screenshots; historical environment instructions, not proof that every current GTK/SWT combination works |
| [results/skia/results.md](../results/skia/results.md) | Early **LibreOffice VCL/UNO** notes: assumptions, native VCL, two-process UNO, and a proposed single-process bridge; not a description of the final custom-widget/Skija architecture |
| [results/skia_vcl.md](../results/skia_vcl.md) | VCL/UNO prototype assessment: separate direct-VCL and UNO routes, partial snippets, integration risks, and reasons for rejecting VCL for this project |
| [results/swing.md](../results/swing.md) | Swing port assessment: working/partial/missing features, native integration questions, screenshots, and explicitly subjective performance impressions |

This map and [Evidence and review](EVIDENCE_AND_REVIEW.md) are additional fork guides. They interpret and index the public record without revising the original assessments.

## Presentation and PDF register

These are named historical artifacts, not source modules or release deliverables. Their paths and Git blob identities were inventoried; their slides/PDF pages were **not** rendered or reviewed in this documentation pass. Titles identify the files, not a new claim about their contents.

| Group | Artifact |
| --- | --- |
| Meetings | [2024-05-17 Kick-Off](../meetings/2024-05-17%20Kick-Off.pptx) |
| Meetings | [2024-05-24 Weekly](../meetings/2024-05-24%20Weekly.pptx) |
| Meetings | [2024-07-09 Eclipse Community Day](../meetings/2024-07-09%20Eclipse%20Community%20Day.pptx) |
| Meetings | [2024-09-13 Intermediate Assessment](../meetings/2024-09-13%20Intermediate%20Assessment.pptx) |
| Meetings | [2025-02-12 State of Work](../meetings/2025-02-12%20State%20of%20Work.pptx) |
| Meetings | [2025-07-08 State of Work](../meetings/2025-07-08%20State%20of%20Work.pptx) |
| Results | [2024-09-13 Intermediate Assessment](../results/2024-09-13%20Intermediate%20Assessment.pptx) |
| Results | [Multiple SWT Display instances support using GTK](../results/Multiple%20SWT%20Display%20instances%20support%20using%20GTK.pptx) |
| Early VCL/UNO notes | [Initiative 31 Skia Summary Brainstorming](../results/skia/Initiative%2031%20Skia%20Summary%20Brainstorming.pdf) |

The two `2024-09-13 Intermediate Assessment.pptx` paths have the same blob ID (`c1d629208f8c1150c066d631b9546dfc7bcb505a`) in the inspected tree. Both paths are retained: an identical stored object does not make either historical navigation location unnecessary.

## Image groups and ownership

All 63 PNG paths belong to the following groups. Read the linked document's captions and surrounding limitations before using an image as evidence. A screenshot can illustrate appearance at one moment; it cannot establish interaction correctness, resource cleanup, performance, or platform parity. The images were inventoried, not visually revalidated in this pass.

| Directory | PNGs | Document that supplies context |
| --- | ---: | --- |
| [report/images](../report/images/) | 9 | [Final report](../report/overall_report.md): technology illustrations, demonstrator screenshots, and incremental replacement diagram |
| [results/images_custom](../results/images_custom/) | 20 | [Custom assessment screenshots](../results/custom.md#screenshots): Button, Text, and project-creation comparisons, including HiDPI examples |
| [results/images_gtk](../results/images_gtk/) | 5 | [GTK appendix](../results/gtk.md#appendix): standalone printing examples |
| [results/images_gtk_themes](../results/images_gtk_themes/) | 8 | [GTK theming walkthrough](../results/gtkCustomTheme.md): configuration and appearance examples |
| [results/images_skia_vcl](../results/images_skia_vcl/) | 8 | [VCL/UNO screenshots](../results/skia_vcl.md#screenshots): paired Windows/prototype snippet images |
| [results/images_swing](../results/images_swing/) | 13 | [Swing assessment](../results/swing.md): technology context and snippet/application appearance |

The remaining tracked file is the unchanged [Eclipse Public License 2.0](../LICENSE). Existing credits remain with their assessments and the report's acknowledgements. This index does not transfer authorship or establish new licensing permissions.

## Coverage and remaining work

- **Complete structural inventory for the pinned snapshot:** every tracked file is classified; every Markdown document has a purpose and a reading boundary above
- **Read:** all 12 Markdown documents; summaries are attributed to the report/assessments rather than promoted to current implementation verification
- **Not applicable here:** source-package/API documentation and a repository application build, because no such source or build surface exists in this snapshot
- **Still unverified:** the 72 binary media files' contents/rendering, live external services and historical contact availability, and current behavior/builds of separate prototypes
- **To finish a claim-specific review:** inspect the original artifact or implementation needed for that claim, record its revision/environment, and keep actual results separate from reported results using the [review workflow](EVIDENCE_AND_REVIEW.md)

Structural coverage of this document repository is not completion of the separate implementation repositories' package documentation or runtime verification.
