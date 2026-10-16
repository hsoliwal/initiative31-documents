<!-- fork-homepage:start -->
# Initiative 31: a reader's map of the SWT research

**Follow the evidence behind an OS-agnostic SWT experiment, from candidate technologies to the final demonstrator and remaining work.** This public `hsoliwal` fork of [swt-initiative31/documents](https://github.com/swt-initiative31/documents) is a research library: reports, assessments, meeting material, presentations, and images. It is useful to developers evaluating the design, readers checking a claim, and contributors choosing a focused next investigation.

## What the project found, and what this fork adds

The [final report](report/overall_report.md) describes a feasibility demonstrator based on custom widgets and Skia. Earlier [VCL](results/skia_vcl.md), [Swing](results/swing.md), and [GTK](results/gtk.md) investigations have their own outcomes and limitations. Read these as distinct approaches; an earlier VCL result is not automatically a result of the later custom-widget demonstrator.

This fork adds reading routes, a document map, evidence guidance, and worked examples. It preserves the original research conclusions and media. It does not provide a runnable SWT distribution or new benchmark evidence. Statements in the historical report are the authors' reported findings, not experiments independently reproduced by this homepage update.

## A small glossary

| Concept | Meaning in this research |
| --- | --- |
| SWT | Eclipse's Standard Widget Toolkit, whose Java API and behavior form the compatibility target |
| OS-agnostic | Sharing implementation across platforms while still handling required platform integration |
| Skia / Skija | A graphics renderer / Java bindings used to access it; drawing alone does not implement all widget behavior |
| VCL / UNO | LibreOffice's widget/windowing layer / component model, explored as an earlier integration route |
| GC | Graphics Context: the SWT drawing API, distinct from a complete widget implementation |
| Demonstrator | An integrated feasibility example, with remaining production work |
| Assessment | A technology-specific record of achievements, risks, and open questions |

## Quick start: read in a useful order

1. Open the [final report](report/overall_report.md) and read its goals, results, and realization plan.
2. Read the [custom-widget assessment](results/custom.md), then compare the alternatives only where your question needs them.
3. Follow the report's code links to the exact implementation repository and branch. This document repository has no application build to run.
4. Use the [content map](docs/CONTENT_MAP.md) for meeting material and presentations, and record dates before comparing conclusions.

Reading on GitHub needs no setup. For a local copy, Git is sufficient:

```sh
git clone --depth 1 https://github.com/hsoliwal/initiative31-documents.git
cd initiative31-documents
git rev-parse HEAD
git ls-files 'report/*' 'results/*.md'
git grep -n -i 'risk' -- report results
```

These commands inspect research files. They do not install, build, or reproduce a prototype. A shallow clone has limited history.

## Worked example: does drawing with Skia establish SWT compatibility?

Start with the custom-widget results and ask which behavior the cited demonstration actually covers. Then consult the final report's remaining work: event handling, a single-canvas implementation, full GC behavior, performance, and widget finalization. A rendering demonstration is evidence about that demonstrated path; it does not by itself establish identical events, accessibility, performance, or platform behavior across applications.

A useful evidence note has five parts: the exact document and revision, the claimed behavior, the observed/reported result, the stated limitation, and the next test needed. If you did not run the code, label the finding “reported” rather than “reproduced.” See the [worked reading examples](docs/READING_EXAMPLES.md) for longer exercises.

## Research cheat sheet

| Your question | Start here | Keep separate |
| --- | --- | --- |
| Why investigate a new SWT implementation? | Final report's goals | Motivation and delivered features |
| Which approach was carried forward? | [Custom assessment](results/custom.md) and final report | Final direction and earlier discarded experiments |
| What happened with LibreOffice reuse? | [Skia/VCL assessment](results/skia_vcl.md) | Direct VCL access and UNO controls |
| What did GTK or Swing demonstrate? | [GTK](results/gtk.md) / [Swing](results/swing.md) | A prototype observation and broad platform guarantees |
| What still needs implementation? | Final report's realization plan | Proposed work, staffing, and release commitments |
| How can I check a quotation? | `git show HEAD:report/overall_report.md` | A versioned source and an evolving branch link |
| How can I review my edit? | `git diff --check` | Clean whitespace and correct research interpretation |

**Go deeper:** [reader guide](docs/START_HERE.md) · [full cheat sheet](docs/CHEATSHEET.md) · [evidence and review guide](docs/EVIDENCE_AND_REVIEW.md) · [collection map](docs/CONTENT_MAP.md) · [license](LICENSE).

## Preserved project introduction and results

<!-- fork-homepage:end -->

> **New to Initiative 31?** Start with the [reader guide](docs/START_HERE.md), use the [research cheat sheet](docs/CHEATSHEET.md), or follow a [worked reading example](docs/READING_EXAMPLES.md).
>
> This is the public `hsoliwal` fork of [swt-initiative31/documents](https://github.com/swt-initiative31/documents). The added guides help navigate the published research; the report's research conclusions, assessments, slides, and license are preserved. The report's internal navigation links are corrected where needed. The upstream introduction follows.

# Initiative 31: Documents

This repository contains documents persisting meeting slides, insights, and assessments of the Initiative 31.

It particularly includes the **[final project report](report/overall_report.md).**

## Reading paths

- [Browse every document group and its coverage](docs/CONTENT_MAP.md)
- [Separate architecture intent, reported results, and verification](docs/EVIDENCE_AND_REVIEW.md)
- [Find the implementation behind a result](docs/START_HERE.md#from-a-report-to-the-right-implementation)
- [Understand the remaining production work](docs/START_HERE.md#what-remains-before-production)
- [Check a claim against its source](docs/CHEATSHEET.md#claim-checking-workflow)

## General Information

Some general information about the initiative, it's motivation, goals and setup can be found in the [kick-off slides](meetings/2024-05-17%20Kick-Off.pptx).

## Results

### Final Report

Initiative 31 has been concluded with a successful demonstrator implementation showing the feasibility of reimplementing Eclipse SWT in an OS-agnostic way and mitigating relevant risks. This makes a productively usable implementation a matter of invested efforts and not of conceptual or technical/technological risks.

**The project is summarized in the [final report](report/overall_report.md).**

### Detailed Results

Results of the prototyping work in the initiative can be found in the `results` folder. A summary is given in [this presentation](results/2024-09-13%20Intermediate%20Assessment.pptx). The individual technologies with links to their specific information are:
- [Skia/VCL](results/skia_vcl.md): Prototype using the Visual Class Library (VCL), the widget library from LibreOffice, together with Skia as a rendering engine
- [Skia/Custom-Drawn](results/custom.md): Prototype using widgets that are custom-drawn with primitive drawing operations using either the OS-native rendering engines or Skia with the Java bindings provided by Skija
- [Swing](results/swing.md): Prototype using the Java-integrated UI framework Swing
- [GTK](results/gtk.md): Prototype using GTK, as already used for the Linux SWT implementation, with its Windows and MacOS ports to reuse the existing SWT GTK implementation on all three major operating systems

Of these technologies, Skia/Custom-Drawn was finally under more detailed investigation while Skia/VCL, Swing, and GTK have been dropped earlier.
