# Worked reading examples

[Reader map](START_HERE.md) · [Cheat sheet](CHEATSHEET.md)

## Example 1: answer “Why not simply use LibreOffice's VCL?”

1. Read [Skia: Developed](../report/overall_report.md#skia-developed) for the final project's account of the change in direction.
2. Open the [Skia/VCL assessment](../results/skia_vcl.md). Read Technology, Achievements, Insights, Risks, and Conclusion together.
3. Distinguish two investigated integration paths: direct VCL access and UNO controls. Do not combine their results into an imaginary complete implementation.
4. Follow the linked code only after recording its branch and revision. The LibreOffice extraction experiment is separate from the later custom-widget demonstrator.

A careful short answer would be: “The project investigated VCL/UNO and recorded useful partial examples, but its final report selected custom widgets over that approach. The VCL assessment describes integration constraints; those are the evidence to inspect before reusing it.”

That statement attributes the decision to its source. It does not assert that VCL is unsuitable for every project.

## Example 2: prepare a decision brief about further work

Use this structure in your own notes:

```text
Question: What would it take to move beyond the demonstrator?
Evidence revision: <commit SHA>
Primary source: report/overall_report.md, Realization Plan
Demonstrated outcome: <specific result, with section link>
Remaining work: <items actually listed in the report>
Assumptions/estimates: <label these separately>
Unverified today: <build, platform, staffing, or compatibility gaps>
Decision needed: <the decision your team actually owns>
```

Read [Follow-Up Tasks](../report/overall_report.md#follow-up-tasks) and [Realization Plan](../report/overall_report.md#realization-plan). Preserve the report's context when quoting capacity estimates. Do not convert its proposal into a current schedule or an approved commitment.

## Example 3: compare technologies without inventing a score

Create one row per question, with four evidence links: custom-drawn, Skia/VCL, GTK, and Swing. Useful questions include widget coverage, browser integration, threading/event handling, platform behavior, maintainability, dependencies, and required skills.

Use these labels:

- **Reported working:** the source explicitly documents the behavior.
- **Reported partial:** read the accompanying limitation.
- **Risk or open question:** the source raises it without resolving it.
- **Not established:** you did not find evidence; that is not the same as impossible.

Start from the [assessment template](../results/_template.md). Avoid adding a numerical ranking without a documented method and comparable measurements.

## Example 4: propose a small documentation fix

For a broken navigation link, a useful PR description contains:

```text
Reader problem: <where navigation fails>
Evidence: <public file URL at an exact commit>
Change: <the corrected target or clearer explanation>
Scope: documentation only; original research conclusions unchanged
Checks: opened relative links, reviewed Markdown, checked diff/whitespace
Not checked: historical prototype build/runtime behavior
```

Keep presentation files and images unchanged when the correction only concerns Markdown. Include a before/after explanation for wording changes that might alter the meaning of a historical result.
