# Initiative 31 research cheat sheet

[Start here](START_HERE.md) · [Examples](READING_EXAMPLES.md) · [Final report](../report/overall_report.md)

## Fast routes

| Need | Read |
| --- | --- |
| Motivation and scope | [Goal](../report/overall_report.md#goal) |
| Timeline and project phases | [Phases](../report/overall_report.md#phases) |
| Selection criteria | [Preselection and Criteria](../report/overall_report.md#preselection-and-criteria) |
| Technology outcomes | [Results](../report/overall_report.md#results) |
| Remaining implementation work | [Follow-Up Tasks](../report/overall_report.md#follow-up-tasks) and [Realization Plan](../report/overall_report.md#realization-plan) |
| Compare candidate risks | The Risks section in [custom](../results/custom.md#risks), [VCL](../results/skia_vcl.md#risks), [GTK](../results/gtk.md#risks), and [Swing](../results/swing.md#risks) |
| Find prototype source | Follow the repository links in the corresponding assessment or final report |

## Read locally in one minute

Requires Git and a terminal. These commands obtain and inspect documents; they do not install or run a prototype.

```sh
git clone --depth 1 https://github.com/hsoliwal/initiative31-documents.git
cd initiative31-documents
git rev-parse HEAD
git ls-files 'report/*' 'results/*.md' 'meetings/*'
git grep -n -i 'risk' -- report results
git grep -n -E '^#{1,4} ' -- report/overall_report.md
```

The shallow clone is convenient for reading the current snapshot. For historical investigation, obtain the needed history deliberately; a missing older commit in a shallow checkout is not proof the commit never existed.

## Command reference

| Task | Command | Result |
| --- | --- | --- |
| Record exactly what you read | `git rev-parse HEAD` | A commit ID to include with notes |
| List assessment Markdown | `git ls-files 'results/*.md'` | Tracked paths, including nested matches |
| Locate references to a technology | `git grep -n -i 'Skija' -- report results` | File and line matches |
| Find headings in the final report | `git grep -n -E '^#{1,4} ' -- report/overall_report.md` | An outline for navigation |
| Inspect the latest changes to a file | `git log -5 --oneline -- report/overall_report.md` | Available history; shallow clones may show only the tip |
| Review your edits | `git diff -- README.md docs report results` | The pending text diff |
| Check whitespace mistakes | `git diff --check` | Whitespace errors, if any |
| List changed paths before proposing edits | `git status --short` | Tracked and untracked changes |

## Claim-checking workflow

1. **Find the claim in the final report.** Use the assessment for supporting detail, rather than assuming the oldest slides are the last word.
2. **Record the evidence.** Save repository, commit, document path, and heading. On GitHub, select a commit-pinned URL when citing a stable snapshot.
3. **Separate categories.** Is the statement an observed result, a project conclusion, a proposal, a requirement, or an estimate?
4. **Read the limitations.** A working example is narrower than complete API compatibility; a feasibility result is narrower than a shipping product.
5. **Check the linked implementation.** Its branch, revision, build instructions, and results must be assessed separately.
6. **Keep uncertainty visible.** State what you did not reproduce and avoid upgrading historic estimates into current commitments.

## Contribution/review checklist

- [ ] The change explains a concrete reader problem.
- [ ] Claims link to public evidence and identify the relevant date/revision.
- [ ] Existing authorship, acknowledgements, licensing, and historical conclusions are retained.
- [ ] Relative paths are checked with exact filename case; links containing spaces are encoded.
- [ ] Images still resolve relative to the document that uses them.
- [ ] No private discussions, credentials, local machine paths, or unpublished plans were added.
- [ ] The diff includes only the intended documents and assets.
- [ ] The PR says what was checked and what was not reproduced.

## Troubleshooting

| Symptom | What to try |
| --- | --- |
| A presentation will not preview on GitHub | Download the existing `.pptx` and open it with a compatible viewer; use Markdown reports for searchable text |
| A report's internal jump link misses its target | Use GitHub's document outline or the corrected direct section links above; headings determine fragment names |
| A historical repository link redirects or has disappeared | Start from the public upstream organization and the final report; record the original citation and verify the replacement before editing |
| Search gives no result | Try the expanded term and abbreviation, and distinguish `Skia`, `Skija`, `VCL`, and `UNO` |
| Two documents appear to disagree | Compare their dates, scope, and project phase before treating them as contradictory |
| You want a build command | Open the linked implementation repository; this collection has no application build or runtime command |

These commands and links were checked against repository contents during documentation authoring. They are a reading/review workflow, not evidence that the historical prototypes were rebuilt or tested.
