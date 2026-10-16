# Evidence, architecture status, and review

[Home](../README.md) · [Collection map](CONTENT_MAP.md) · [Reading examples](READING_EXAMPLES.md)

## What is described versus what is verified

The [final report](../report/overall_report.md) is the project's account of its demonstrator and proposed next steps. This guide was checked against the public document snapshot [at `1a5720a`](https://github.com/hsoliwal/initiative31-documents/tree/1a5720a31a1b423548eee3c9a5bb3bfcdbac17fd). It does not inspect or execute the current implementation repositories. Use **reported** when describing their behavior from this collection; reserve **reproduced** for a check actually run on a recorded implementation revision.

## Architecture: intent and reported state

| Concern | What the report establishes | What remains separate |
| --- | --- | --- |
| SWT API compatibility | [Goal](../report/overall_report.md#goal) targets a replacement with compatible features/API | A goal is not an API-conformance result |
| Custom widgets and rendering | [Skia results](../report/overall_report.md#skia-developed) describe custom widget drawing through SWT's `GC`, adapted to Skia | Skia supplies drawing capabilities; it does not supply complete SWT widget semantics by itself |
| Incremental migration | [Incrementality](../report/overall_report.md#incrementality) describes keeping native widgets working while replacing them progressively | The reported migration strategy does not mean native dependencies have all been removed |
| Native widget backing and events | [Content / Steps](../report/overall_report.md#content--steps) says widgets remain natively backed and much event handling remains OS-provided | Custom event handling and moving to one canvas are proposed completion work |
| Graphics API | The same [steps](../report/overall_report.md#content--steps) say the GC adaptation covers the rendering needed by the demonstrator | Full existing-GC functionality still needs finalization |
| Rendering performance | The report records dedicated experiments and identifies an extra rendering-buffer copy | An end-to-end speedup across all platforms, workloads, and widgets is not established by this documentation review |
| Widget completeness | [Achievements](../report/overall_report.md#achievements) and [steps](../report/overall_report.md#content--steps) describe preliminary implementations and remaining capabilities | Basic rendering coverage is not full behavior, accessibility, lifecycle, or compatibility validation |
| Production effort | [Capacity / Effort](../report/overall_report.md#capacity--effort) gives a scoped estimate and staffing recommendation | This is not current funding, staffing, an accepted delivery date, or a release commitment |

The earlier [custom-drawn assessment](../results/custom.md#skia-based-gc) describes wrapping an OS-specific GC, rendering via a Skia-based GC, then copying the result back. It also names an `IGraphicsContext` interface. Those are **reported historical implementation details**; this repository neither declares that interface nor proves its current signature in a separate prototype.

Likewise, the [VCL/UNO notes](../results/skia/results.md#single-process-uno-approach) describe a bridge that would need to be constructed. Do not document that proposed C/FFM bridge as an implemented API or combine it with the later custom-widget demonstrator.

## Two examples of a defensible answer

### Does GTK browser integration work?

The [GTK assessment's Results](../results/gtk.md#results) distinguishes building mixed GTK/Win32 binaries from browser snippets failing at runtime. A source-backed answer is: “The assessment reports successful binary construction, but browser integration was still failing at runtime in that experiment.” Record the source revision and platform. A successful compilation, a standalone print demo, or an unrelated screenshot cannot turn that into a working-browser result.

### Is Swing performance proven acceptable?

The [Swing Risks section](../results/swing.md#risks) explicitly says performance was subjective and lacked automated benchmarks. A source-backed answer is: “The authors reported acceptable interactive impressions, with benchmarking still missing.” To establish more, define a workload, record implementation/toolchain/OS revisions, measure it, and report the observations and limitations. Do not compare that impression numerically with GTK's reported timings as if both used a common benchmark protocol.

## Contributing without changing historical meaning

For a guide or navigation correction, edit this fork's `README.md` or `docs/`. Keep source conclusions, contributor credits, slides, screenshots, and licensing intact. If proposing a correction to original findings, identify it explicitly, cite public evidence, and check the original upstream repository's current instructions and review arrangements.

For a new assessment, use [the existing template](../results/_template.md). Its sections separate technology and skills, contributors and effort, achievements, insights, risks, and conclusion. Fill placeholders from evidence; an unfilled template is not another evaluated technology. Keep new findings distinguishable from the historical record, with an experiment date and implementation revision.

| Proposed change | Minimum evidence and review |
| --- | --- |
| Path or heading repair | Exact repository/path/case, existing target heading, and rendered or static target check |
| Paraphrase of a report | Original document revision and section; preserve scope, uncertainty, and technology/phase |
| New reproduction result | Implementation commit, environment, procedure, actual result, and limitations; update the relevant implementation documentation separately |
| New screenshot or slide interpretation | Open the artifact, identify page/frame/context, and state what it does and does not show |
| New benchmark comparison | Comparable workload/setup, measurements and method, repeated-run policy, and environment; no inferred numbers |

Use this compact review record rather than a blanket “tested” claim:

```text
Changed paths:
Public source revision and section:
Claim status: reported / reproduced / proposed / unresolved
Checks actually performed and results:
Checks not performed and why:
Remaining question or required evidence:
```

## Verification gates

1. **Scope:** inspect the exact diff and changed-file list. Confirm the intended Markdown-only change and retention of original attribution.
2. **Navigation:** check relative paths against the complete tracked tree, including filename case and URL-encoded spaces. Check heading fragments against the target document at the same revision. Include image references if edited.
3. **Meaning:** compare claims with their cited sections. Retain distinctions between wish, reported result, demonstrated feasibility, proposed work, and current reproduction.
4. **Presentation:** preview changed Markdown. Static path/fragment checks cannot certify the rendered layout or binary media readability.
5. **External evidence:** open new external targets as needed and record what was actually checked. A retained link or a successful page read does not validate an implementation, channel availability, or remote build.
6. **Delivery:** record the exact documentation commit and changed paths after publication. Any CI check must refer to that commit; absence of a configured build is not a passing build.

No application compiler, linter, test runner, or CI workflow is defined in the inspected document-only tree. Documentation review is applicable; prototype builds, GUI tests, and cross-platform checks were **not run** by this pass. Binary media were inventoried only. These limits keep the collection useful without implying that documentation maintenance reproduces the research.
