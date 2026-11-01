# Book-Length Project Playbook

**Purpose:** Reusable starting context for technical or scholarly book-length projects developed collaboratively with an AI writing or coding agent.

**Status:** Draft v0.4 — intended to be refined over time.

---

# 1. What this document is for

This document defines a reusable working method for producing rigorous, polished, book-length technical or scholarly works.

It is intended to preserve the decisions that otherwise tend to be rediscovered through repeated prompting:

- editorial and pedagogical style,
- mathematical and citation conventions,
- repository organization,
- manuscript/build workflow,
- figure standards,
- exercise and workbook conventions,
- quality-control and release procedures,
- and the expected collaboration pattern between author and an AI agent.

It should be supplied near the beginning of a new project, then supplemented with a short project-specific brief.

This document is **not** intended to prescribe the subject matter, thesis, or chapter structure of every future book. Those should be established separately for each project.

---

# 2. Project-specific brief

At the start of each new book, define the following before substantial drafting begins.

## 2.1 Working title

`<working title>`

## 2.2 Subject and scope

State:

- the central subject,
- the intended breadth and depth,
- important exclusions,
- whether the goal is a textbook, monograph, survey, synthesis, tutorial, reference work, or hybrid.

## 2.3 Intended audience

Specify expected background as concretely as possible.

Example:

> Technically sophisticated readers with undergraduate mathematics, programming experience, and familiarity with machine learning, but without specialist training in the book's core discipline.

The manuscript should not silently assume substantially more background than this.

## 2.4 Pedagogical goal

Specify what a successful reader should be able to do after reading the book.

Prefer concrete outcomes such as:

- understand the central conceptual framework,
- derive major results,
- recognize common misconceptions,
- connect theory to applications,
- interpret modern research,
- solve representative problems.

## 2.5 Desired voice

Default:

- rigorous but readable,
- technically precise,
- explanatory rather than performative,
- professional but not stiff,
- intuition first where useful, followed by formalization,
- no unnecessary jargon,
- no rhetorical inflation,
- no casual oversimplifications that become false.

## 2.6 Mathematical level

State expected prerequisites, for example:

- algebra,
- calculus,
- multivariable calculus,
- linear algebra,
- probability,
- basic statistics,
- optimization,
- programming.

Also state which concepts should be introduced from first principles despite technically capable readership.

## 2.7 Research standard

Decide whether the project is:

- primarily expository,
- research-informed,
- literature-review-heavy,
- or intended to make original synthetic arguments.

For research-informed projects, prefer primary sources for foundational claims and strong review literature for broad consensus.

## 2.8 Source-governance standard

For research-heavy books, decide at project startup how claims will remain traceable to evidence.

At minimum, preserve enough source context that a later reviewer can determine:

- which source supports a nontrivial factual or historical claim,
- whether the source is primary, secondary, or a review,
- whether the claim is broadly accepted, contested, or interpretive,
- whether the manuscript is paraphrasing a source or advancing its own synthesis,
- and which claims should be rechecked before publication because the literature may have changed.

A lightweight chapter-level research ledger is often sufficient.

For research-heavy projects, use a repository-level file such as:

```text
RESEARCH_LEDGER.md
```

or, for larger projects, a directory such as:

```text
research/
    chapter-03.md
    chapter-04.md
    ...
```

A useful entry format is:

```markdown
## <Claim, topic, or subsection>

**Manuscript location:** Chapter <n>, section <name>

**Claim / question:**  
<What the manuscript is asserting or what needs to be established>

**Sources:**
- <citation key or source> — <primary / secondary / review / institutional>
- <citation key or source> — <source type>

**Consensus / confidence:**  
<well established / broadly accepted / contested / minority view / uncertain / interpretive>

**What the sources actually support:**  
<short note distinguishing the evidence from the manuscript's synthesis>

**Caveats / disagreements:**  
<important limitations, disputes, or scope conditions>

**Recheck before release:**  
<yes/no, with reason if yes>
```

The ledger does not need an entry for every citation. Use it where provenance could otherwise become difficult to reconstruct, especially for:

- important historical claims,
- controversial or disputed claims,
- empirical claims central to the book's argument,
- cross-disciplinary syntheses,
- claims based on several partially conflicting sources,
- fast-moving research,
- legal or regulatory claims,
- or passages where the manuscript advances an interpretation beyond what any one source states explicitly.

### Research-ledger discipline

The ledger should:

- remain concise,
- record the evidentiary basis rather than duplicate source summaries,
- distinguish source claims from authorial synthesis,
- preserve meaningful disagreement rather than flatten it into false consensus,
- and identify time-sensitive claims that should be rechecked before release.

Do not use it as a bibliography substitute. Formal citations still belong in the manuscript and `references.bib`.

Do not create administrative overhead merely for completeness. The goal is to prevent polished prose from becoming detached from its evidentiary basis.

---

# 3. Project startup protocol

Before substantial chapter drafting begins, follow a deliberate startup sequence.

1. **Read this playbook and the project-specific brief.**
2. **Interrogate the proposed scope.** Identify ambiguities, hidden prerequisites, likely omissions, and places where the project is too broad or too narrow.
3. **Clarify the organizing thesis.** A book should have a reason for its sequence and emphasis beyond being a collection of related topics.
4. **Propose plausible architectures.** When the structure is not obvious, compare two or three chapter organizations and explain their tradeoffs.
5. **Set research and notation standards.** Establish source expectations, decide whether a research ledger is warranted, define mathematical prerequisites, notation conventions, and any domain-specific terminology rules.
6. **Identify project risks.** Examples include unstable current research, unusually difficult sourcing, heavy mathematical notation, large numbers of figures, or dependence on external data.
7. **Scaffold the repository.** Create the initial manuscript structure, bibliography, build configuration, quality checks, and `PROJECT_STATE.md`.
8. **Build a minimal end-to-end artifact.** Produce a small PDF immediately, even if it contains only placeholder chapter material. This validates the production pipeline before substantial prose accumulates.
9. **Record the initial project state.** Note the current phase, settled conventions, open decisions, and next priorities.
10. **Draft only after the architecture and pipeline are credible.**

The startup process should challenge weak assumptions rather than merely formalize the author's first outline.

---

# 4. Editorial principles

## 4.1 Explain before compressing

A technically correct sentence is not necessarily pedagogically useful.

When introducing a difficult idea:

1. motivate the problem,
2. give the intuition,
3. present the formal definition,
4. derive or justify the result,
5. show an example,
6. explain what the result means,
7. note limitations or common misunderstandings.

Do not use formulas as substitutes for explanation.

## 4.2 Distinguish levels of claim

Maintain clear distinctions among:

- definition,
- theorem,
- derivation,
- empirical result,
- interpretation,
- analogy,
- heuristic,
- historical claim,
- contested claim,
- author's synthesis.

Avoid allowing an analogy to quietly become a definition.

## 4.3 Preserve nuance

Do not force superficially similar concepts into a stronger unification than the mathematics or literature supports.

When several fields use similar mathematical structures, distinguish:

1. formal mathematical equivalence,
2. interpretive or statistical relationship,
3. operational or physical relationship.

This distinction is often important in interdisciplinary books.

## 4.4 Avoid false simplification

Prefer:

> "A useful intuition is..."

over:

> "X is just..."

when the latter would erase important structure.

Avoid textbook clichés that are pedagogically familiar but technically misleading.

## 4.5 Derivations should show the important steps

Do not skip algebraic or conceptual steps that a motivated non-specialist reader is likely to wonder about.

A good derivation should make clear:

- what is being substituted,
- which identity or theorem is being used,
- why a rearrangement is legal,
- where an assumption enters,
- and what the resulting expression means.

Routine arithmetic may be compressed; non-obvious transformations should not be.

## 4.6 Historical material should explain conceptual development

History is most valuable when it explains:

- what problem motivated a concept,
- what earlier formulation was insufficient,
- how the modern formulation changed the field,
- which distinctions emerged later.

Avoid decorative name-and-date lists.

---

# 5. Chapter architecture

Chapters need not be mechanically identical, but the following pattern is a strong default.

## 5.1 Opening

Each chapter should establish:

- the problem or question,
- why it matters,
- what the reader should learn,
- how it connects to earlier chapters.

## 5.2 Conceptual development

Introduce the main idea informally before relying on dense notation where possible.

## 5.3 Formal development

Definitions, propositions, derivations, and equations should follow naturally from the conceptual setup.

## 5.4 Examples

Use examples that illuminate structure rather than merely substitute numbers into formulas.

Prefer examples that expose:

- edge cases,
- counterintuitive behavior,
- common errors,
- practical consequences.

## 5.5 Connections

Where useful, explain connections to:

- adjacent disciplines,
- machine learning,
- statistics,
- physics,
- philosophy,
- engineering,
- economics,
- computation,
- or the historical development of the topic.

Do not add cross-disciplinary material merely for breadth.

## 5.6 Chapter close

A short synthesis is useful when a chapter contains several conceptual layers.

The closing should emphasize what changed in the reader's understanding rather than simply recapitulating headings.

---

# 6. Exercises

For projects that include exercises, each substantive chapter should usually contain a small, varied problem set.

A useful mix is:

- conceptual questions,
- short derivations,
- quantitative problems,
- interpretation questions,
- application problems,
- one more demanding synthesis problem where appropriate.

Exercises should test understanding developed in the chapter rather than introduce essential material that was never explained.

Exercise numbering should remain stable once the manuscript is nearing completion.

---

# 7. Companion hints-and-solutions workbook

When a solutions companion is included, keep it separate from the main book.

Each exercise solution should use the following structure.

## Hint

Give the smallest useful nudge that could get a stuck student moving.

A good hint:

- identifies the relevant concept,
- suggests a first step,
- or points to a useful equation,

but does not reveal the full solution.

## Step-by-step solution

Show the reasoning explicitly.

For mathematical problems:

- define variables,
- state formulas,
- substitute carefully,
- show important rearrangements,
- compute,
- interpret.

For conceptual problems:

- identify the governing principle,
- distinguish nearby concepts,
- reason through the implications,
- state the conclusion.

## Result and interpretation

End with a concise statement of the result and why it matters.

The workbook should preserve exercise numbering and titles exactly.

---

# 8. Mathematical typesetting

## 8.1 Source format

Markdown is the canonical manuscript source unless there is a strong project-specific reason to use another format.

Use LaTeX syntax for mathematics.

## 8.2 Inline mathematics

Use:

```text
$...$
```

for short inline expressions.

## 8.3 Display mathematics

Use single physical-line display blocks whenever practical:

```text
$$...$$
```

For multiline derivations, use an internal LaTeX environment such as:

```text
$$\begin{aligned}
...
\end{aligned}$$
```

This improves compatibility with both GitHub rendering and Pandoc/LaTeX.

## 8.4 Compatibility

Mathematics should render correctly in:

- GitHub Markdown,
- Pandoc,
- LaTeX/PDF.

Avoid commands known to be poorly supported by GitHub Markdown when a portable equivalent exists.

Prefer conventional LaTeX operators such as:

```text
\mathrm{KL}
\ln
\log
\exp
\Pr
```

rather than fragile custom constructions.

## 8.5 Notation discipline

Maintain a notation glossary for books with substantial mathematics.

Notation should be:

- introduced before use,
- consistent across chapters,
- reused rather than reinvented,
- and checked globally before release.

---

# 9. Citations and bibliography

Use a project-level BibTeX file, normally:

```text
references.bib
```

Use citation keys consistently in the Markdown source.

## 9.1 Source hierarchy

Prefer, roughly:

1. original primary papers for foundational results,
2. authoritative monographs or textbooks,
3. high-quality review papers,
4. institutional or professional sources,
5. secondary explanatory sources only where appropriate.

## 9.2 Citation placement

Citations should support meaningful factual, historical, or research claims.

Do not cite every sentence mechanically.

Do cite:

- historical priority,
- empirical claims,
- contested interpretations,
- named results,
- modern research claims,
- specific technical developments.

## 9.3 Final bibliography checks

Before release:

- verify that every citation key resolves,
- identify unused bibliography entries,
- inspect formatting,
- and spot-check important references manually.

---

# 10. Figures

Figures should be treated as publication assets, not incidental plotting output.

## 10.1 Goals

A figure should:

- explain something that prose alone explains less efficiently,
- have clear visual hierarchy,
- remain legible in print,
- use consistent typography,
- use restrained color,
- avoid gratuitous decoration,
- and visually match the quality of the manuscript.

## 10.2 Figure classes

Distinguish between:

### Analytical plots

Examples:

- probability distributions,
- loss functions,
- parameter relationships.

These are naturally reproducible from code.

### Conceptual diagrams

Examples:

- state-space mappings,
- process diagrams,
- decompositions,
- physical thought experiments.

These should be designed as diagrams rather than forced into generic plotting aesthetics.

## 10.3 Curated publication assets

If the final figures have been manually or externally art-directed, treat the committed files in:

```text
figures/
```

as canonical publication assets.

Do **not** automatically regenerate them during normal builds.

Any figure-generation script should write to a preview directory by default, for example:

```text
output/generated-figures-preview/
```

Overwriting curated assets should require an explicit opt-in flag.

## 10.4 Figure references

Figure paths in chapter Markdown should work both on GitHub and during PDF generation.

The PDF build should use resource paths rather than requiring source paths to be rewritten.

---

# 11. Repository structure

A good default repository layout is:

```text
/
├── README.md
├── STYLE_GUIDE.md
├── LICENSE.md
├── book.md
├── metadata.yaml
├── references.bib
├── RESEARCH_LEDGER.md        # optional for research-heavy projects
├── pyproject.toml
├── uv.lock
│
├── chapters/
│   ├── 00-preface.md
│   ├── 01-...
│   ├── 02-...
│   └── ...
│
├── appendices/
│   ├── a-...
│   └── b-...
│
├── figures/
│   └── ...
│
├── workbook/
│   ├── 00-introduction.md
│   └── ...
│
├── latex/
│   └── header.tex
│
├── scripts/
│   ├── build.sh
│   ├── build.ps1
│   ├── build_workbook.sh
│   ├── build_workbook.ps1
│   ├── check.sh
│   ├── check.ps1
│   ├── normalize_math.py
│   ├── generate_figures.py
│   └── index.lua
│
└── output/
    └── ...
```

Not every project needs every directory.

The repository itself is the canonical source of truth.

## Project state file

For long-running projects, maintain a lightweight:

```text
PROJECT_STATE.md
```

This file is a handoff and continuity aid, especially when:

- work may move between different AI agents,
- the project may pause for weeks or months,
- multiple chapters are in different states of completion,
- unresolved editorial or technical decisions remain,
- or the next task is not obvious from Git history alone.

It should summarize current project state, not duplicate the manuscript or become a second issue tracker.

A useful template is:

```markdown
# Project State

## Current phase

<e.g. core drafting, figure pass, whole-manuscript revision>

## Completed

- <major completed milestone>
- <major completed milestone>

## In progress

- <current work item>
- <current work item>

## Next priorities

1. <next highest-value task>
2. <next task>
3. <next task>

## Open decisions

- <decision not yet settled>
- <decision not yet settled>

## Known issues / technical debt

- <known inconsistency, build issue, citation gap, etc.>

## Important conventions currently in force

- <project-specific convention that a new agent could otherwise miss>

## Last validated state

- Main build: <pass/fail, date or commit if useful>
- Workbook build: <pass/fail/not applicable>
- Repository checks: <pass/fail>
- Release status: <e.g. unreleased, v0.3 draft, v1.0.0>
```

### Update discipline

Update `PROJECT_STATE.md` when:

- a major phase changes,
- a substantial milestone is completed,
- priorities materially change,
- an important unresolved decision is introduced or resolved,
- or work is about to be handed to another agent or paused.

Do not update it for every minor edit.

The state file should remain concise enough that a new agent can read it in a few minutes.

Do not use it as a substitute for:

- Git history,
- issue tracking,
- detailed research notes,
- source citations,
- or manuscript content.

If the file becomes long or historical, prune resolved material rather than letting it become a chronological log.

## Research ledger

When the project is research-heavy, maintain `RESEARCH_LEDGER.md` or chapter-level research ledger files as described in the source-governance section.

This file is not a status tracker. It exists to preserve the relationship among:

- important manuscript claims,
- supporting sources,
- level of consensus,
- caveats,
- and authorial synthesis.

`PROJECT_STATE.md` answers **"Where is the project now?"**

The research ledger answers **"Why do we believe or assert this?"**

## Artifact classes

Classify important files conceptually so an agent knows what may be regenerated.

### Canonical source

Human- or agent-authored material whose current checked-in form is authoritative, for example:

- chapter Markdown,
- bibliography,
- notation conventions,
- hand-curated or art-directed figures,
- license text.

These must not be overwritten merely because a generator exists.

### Generated but intentionally committed

Artifacts that are generated yet deliberately versioned because they are part of the distributable project or needed without the generation toolchain.

Regeneration should be explicit and reviewed.

### Generated and disposable

Build products and intermediates such as:

- PDFs,
- generated TeX,
- preview figures,
- temporary renderings,
- caches.

These should normally live under `output/` or another ignored build directory.

When in doubt, prefer preserving a potentially canonical asset over regenerating it.

---

# 12. Build system

A mature project should be locally reproducible.

A useful toolchain is:

- Markdown source,
- Pandoc,
- BibTeX-compatible bibliography,
- LaTeX,
- `pdflatex`,
- `makeindex`,
- Python via `uv`,
- Git.

## 12.1 Python environment

Use:

```bash
uv sync
```

and run project Python tools with:

```bash
uv run python ...
```

Avoid requiring manual virtual-environment activation.

## 12.2 Main PDF build

Provide both:

```text
scripts/build.sh
scripts/build.ps1
```

where practical.

The build should:

1. validate required system tools,
2. run Pandoc,
3. run citation processing,
4. generate LaTeX,
5. run LaTeX,
6. run indexing if applicable,
7. rerun LaTeX enough times to resolve references,
8. place final artifacts in `output/`.

## 12.3 Workbook build

The companion workbook should have a separate build target.

## 12.4 Builds should not mutate source assets

A normal book build must not:

- rewrite manuscript Markdown,
- regenerate curated figures,
- update lockfiles,
- or modify committed source files.

Build outputs belong in `output/`.

---

# 13. Repository checks

Provide lightweight repository checks separate from full PDF compilation.

A default check should include:

- dependency synchronization,
- math-format validation,
- Python syntax/compile checks,
- optionally Markdown linting.

Example:

```bash
bash scripts/check.sh
```

The checks should be fast enough to run frequently.

---

# 14. Indexing

For substantial reference-oriented books, include a conventional subject index.

Index terms should be inserted invisibly into Markdown source rather than cluttering prose.

Example convention:

```html
<!-- index: Kullback--Leibler divergence; entropy!relative -->
```

A Pandoc filter can convert these into LaTeX `\index{...}` commands.

Indexing should include:

- major concepts,
- named results,
- important people where historically relevant,
- synonyms,
- useful subentries,
- selective cross-references.

Do not index every mention.

---

# 15. PDF typography and layout

The PDF should look like a book, not a Markdown printout.

Default priorities:

- readable serif body text,
- stable heading hierarchy,
- professional margins,
- consistent equation spacing,
- clear figure captions,
- restrained use of color,
- running headers where useful,
- page numbers,
- proper table of contents,
- bibliography,
- index when appropriate.

Inspect especially:

- TOC alignment,
- long section numbers,
- running headers,
- widows/orphans,
- figure scaling,
- equation overflow,
- tables,
- hyperlinks,
- index columns.

Warnings should be reviewed rather than ignored automatically.

---

# 16. Cross-platform considerations

Avoid platform-fragile assumptions unless the project explicitly targets one environment.

Important practices:

- use explicit UTF-8 file I/O,
- avoid hard-coded platform-specific paths,
- keep generated outputs and source files clearly separated,
- provide shell/PowerShell equivalents when that materially improves usability,
- avoid unnecessary executable-bit or line-ending churn,
- handle host-specific path separators correctly,
- prefer command-line build dependencies over fragile GUI-only workflows.

When the author primarily works on Windows, Git Bash and PowerShell compatibility are useful implementation targets, but they are not defining requirements of the playbook.

---

# 17. Repository change workflow

The checked-out repository is the canonical source of truth once one exists.

The exact handoff workflow depends on whether the agent has direct repository access.

## 17.1 When the agent has direct repository access

Examples include Codex or another coding/writing agent operating inside the repository.

The agent should:

- read the current files before modifying them,
- work directly against the checked-out repository rather than reconstructing files from conversation memory,
- make narrowly scoped, reviewable changes,
- run relevant checks and builds locally,
- inspect `git diff` or equivalent before declaring work complete,
- avoid unrelated cleanup or formatting churn,
- and leave the repository in a state the author can review and commit confidently.

Whether the agent itself creates commits is project-specific. If it does, commits should be logically scoped and have descriptive messages.

## 17.2 When the agent does not have direct repository access

The user's repository remains canonical.

Prefer:

- narrow tested patches for text/code changes,
- complete replacement files when a patch is unnecessarily fragile,
- and archives of publication assets for binary replacements.

Recommended user workflow:

```bash
git pull --rebase
git apply --check /c/Users/<user>/Downloads/change.patch
git apply /c/Users/<user>/Downloads/change.patch
```

Then validate before committing.

Avoid binary Git patches when the underlying assets may have been regenerated locally; their content hashes make such patches brittle.

## 17.3 In either mode

- Never assume an old snapshot is current merely because it was correct earlier in the project.
- Avoid modifying unrelated or frequently drifting files without need.
- Preserve established project conventions unless explicitly changing them.
- If the baseline differs from expectations, diagnose the mismatch rather than forcing a risky update.

---

# 18. Collaboration workflow with an AI agent

This section is especially important.

## 18.1 Work from artifacts, not summaries alone

Once a repository exists, the actual files should be treated as authoritative.

Do not reconstruct chapters or configuration from memory if current files are available.

When `PROJECT_STATE.md` exists, read it early in a new work session, but verify important claims against the current repository rather than treating the state file as infallible.

When a research ledger exists, consult it before materially revising research-dependent passages. Update it when a revision changes the evidentiary basis, consensus characterization, or important caveats.

## 18.2 Prefer implementation over repeated planning

When the direction is clear, move directly to:

- drafting,
- editing,
- validating,
- building,
- or producing the patch.

Avoid repeatedly restating the intended plan without making progress.

## 18.3 Preserve agreed decisions

Once an editorial or architectural choice is settled, treat it as a project convention until explicitly changed.

Do not re-litigate established decisions casually.

## 18.4 Separate conceptual review from mechanical editing

For major revisions, distinguish:

- substantive conceptual problems,
- pedagogical improvements,
- stylistic copy edits,
- mechanical formatting changes.

This makes review easier and reduces accidental regressions.

## 18.5 Make changes incrementally

Large books should be developed in reviewable increments.

Good units include:

- one chapter,
- a small group of chapters,
- one figure pass,
- one exercise pass,
- one indexing pass,
- one final copy-edit pass.

## 18.6 Validate changes before handoff

When the agent has direct repository access:

- inspect the resulting diff,
- run the relevant checks and builds,
- and verify that only intended files changed.

When the agent is handing off a patch:

- apply it to a clean copy of the expected baseline,
- run relevant validation,
- ensure paths are repository-relative,
- and avoid binary patching where baseline hashes are uncertain.

## 18.7 Own baseline mismatches

If a change fails because the assumed baseline was wrong, diagnose the mismatch and generate or apply a safer correction.

Do not force the author into complicated Git recovery merely to preserve an agent-generated change.

## 18.8 Keep changes conceptually scoped

Direct repository access makes change discipline more important, not less.

Do not casually combine unrelated work such as:

- conceptual chapter revision,
- build-system refactoring,
- figure redesign,
- bibliography cleanup,
- and copy editing

in one opaque change set.

A change may span many files when the task genuinely requires it, but the reason for that span should be clear. Reviewability is a project-quality feature.

---

# 19. Recommended project phases

A useful default lifecycle is:

## Phase 1 — Concept and scope

Develop:

- purpose,
- thesis or organizing framework,
- audience,
- prerequisites,
- scope,
- chapter architecture,
- research standard,
- and, where appropriate, a research-ledger convention.

## Phase 2 — Repository scaffold

Create:

- directory structure,
- metadata,
- bibliography,
- style guide,
- build scripts,
- math validation,
- initial README,
- `PROJECT_STATE.md`.

Build a minimal PDF immediately and record the initial validated state.

## Phase 3 — Core manuscript

Draft chapters incrementally.

After each substantial group:

- build,
- inspect,
- revise,
- commit or otherwise checkpoint the work.

### Periodic integration passes

After roughly every three or four substantive chapters, or whenever a major conceptual arc closes, perform a whole-project integration pass.

Check for:

- terminology drift,
- notation drift,
- repeated explanations,
- missing prerequisites,
- contradictory assumptions,
- stale forward references,
- broken backward references,
- chapter-depth imbalance,
- architectural dependencies that have emerged during drafting,
- and research claims whose source support or consensus characterization has drifted during revision.

These passes should be lighter than the final whole-manuscript revision, but they should happen early enough to prevent local decisions from hardening into global inconsistencies.

## Phase 4 — Exercises

Add exercises after chapter exposition is reasonably stable.

## Phase 5 — Figures

Add or redesign figures once the conceptual content they represent has stabilized.

## Phase 6 — Companion workbook

Develop hints and step-by-step solutions after exercise numbering has stabilized.

## Phase 7 — Whole-manuscript revision

Review for:

- conceptual continuity,
- repeated explanations,
- inconsistent terminology,
- notation drift,
- unsupported claims,
- stale forward references,
- uneven chapter depth.

## Phase 8 — Index and appendices

Add:

- notation glossary,
- technical appendices,
- subject index.

## Phase 9 — Final production pass

Perform:

- copy editing,
- citation audit,
- bibliography audit,
- figure inspection,
- layout inspection,
- PDF preflight,
- build validation.

## Phase 10 — Release

Add:

- license,
- version tag,
- release artifact,
- optional checksum,
- optional GitHub release.

---

# 20. Final QA checklist

Before declaring a release candidate complete:

## Manuscript

- [ ] Chapter ordering is correct.
- [ ] Cross-references are correct.
- [ ] Terminology is consistent.
- [ ] Notation is consistent.
- [ ] No stale "later we will..." references remain.
- [ ] Exercises match chapter material.
- [ ] Workbook numbering matches exercises exactly.

## Mathematics

- [ ] Math compatibility checker passes.
- [ ] Important derivations have been manually reviewed.
- [ ] Units and logarithm bases are explicit where relevant.
- [ ] No unsupported notation is used before introduction.

## References

- [ ] No missing citation keys.
- [ ] No accidental unused bibliography entries.
- [ ] Foundational claims use authoritative sources.
- [ ] Historical claims have been spot-checked.
- [ ] Research-ledger entries, where used, still match the manuscript.
- [ ] Contested claims are represented with appropriate nuance.
- [ ] Time-sensitive claims marked for rechecking have been revalidated.

## Figures

- [ ] Every figure is legible at final PDF size.
- [ ] Labels are readable.
- [ ] Captions are informative.
- [ ] Figures use a consistent visual language.
- [ ] Normal builds do not overwrite curated assets.

## PDF

- [ ] Full build succeeds.
- [ ] No unresolved references.
- [ ] No missing figures.
- [ ] No meaningful overfull boxes.
- [ ] TOC inspected visually.
- [ ] Representative equation-heavy pages inspected.
- [ ] Representative figure-heavy pages inspected.
- [ ] Bibliography inspected.
- [ ] Index inspected.
- [ ] PDF opens correctly and is not accidentally encrypted or malformed.

## Repository

- [ ] Working tree clean before release.
- [ ] Build instructions work.
- [ ] `PROJECT_STATE.md` reflects the actual project phase and release status.
- [ ] Canonical and generated artifacts are clearly distinguished.
- [ ] Normal builds do not mutate canonical source assets.
- [ ] License present.
- [ ] Version committed.
- [ ] Release tag points to intended commit.

---

# 21. Licensing default

Licensing is project-specific, but a useful default for noncommercial educational books is:

### Manuscript, workbook, appendices, and original figures

**Creative Commons Attribution–NonCommercial–NoDerivatives 4.0 International (CC BY-NC-ND 4.0)**

This supports:

- personal use,
- intact noncommercial redistribution,
- attributed noncommercial excerpts,

while restricting:

- commercial use,
- distribution of adapted versions without permission.

### Build and helper scripts

A permissive software license such as **MIT** is appropriate.

Keep the scope of the content license and software license explicit.

---

# 22. Decisions that should remain project-specific

Do not automatically carry the following from one book to another:

- chapter count,
- chapter titles,
- central thesis,
- degree of historical coverage,
- number of exercises,
- number of figures,
- whether a workbook is needed,
- whether an index is needed,
- exact licensing choice,
- exact mathematical prerequisites.

The playbook defines **how to build the book**, not what every book must contain.

---

# 23. High-value defaults for future projects

Unless the new project gives a reason to change them, begin with these defaults:

1. Markdown as canonical manuscript source.
2. Pandoc + LaTeX for PDF production.
3. Git repository as source of truth.
4. `uv` for Python tooling.
5. One Markdown file per chapter.
6. Central BibTeX bibliography.
7. Explicit notation discipline.
8. Intuition followed by formal development.
9. Primary-source preference for foundational claims.
10. Exercises only after exposition is reasonably stable.
11. Separate hints-and-solutions workbook.
12. Curated figures treated as publication assets.
13. Fast repository checks plus separate full PDF build.
14. Repository-aware collaboration: direct edits when access exists, tested handoffs otherwise.
15. Explicit source governance for research-heavy projects.
16. Periodic whole-book integration passes during drafting.
17. Whole-manuscript revision before final copy edit.
18. Visual PDF inspection before release.
19. Release tags treated as immutable once published.
20. Lightweight `PROJECT_STATE.md` for continuity and agent handoff.
21. Optional research ledger for claim-to-source traceability in research-heavy projects.

---

# 24. Suggested initial prompt for a future project

The following can be used together with this file:

> I want to develop a book-length project using the attached Book-Length Project Playbook as our default process and production standard.
>
> The subject is: **[subject]**
>
> The intended audience is: **[audience]**
>
> The main goal is: **[goal]**
>
> Expected mathematical/technical background: **[background]**
>
> Desired scope: **[scope]**
>
> Important topics to include: **[topics]**
>
> Important topics to exclude or deemphasize: **[exclusions]**
>
> Desired balance among intuition, mathematical rigor, history, applications, and current research: **[balance]**
>
> Follow the playbook's startup protocol before drafting substantial prose. Challenge weak assumptions or scope choices rather than merely accepting them. Help me settle the organizing thesis, chapter architecture, research standard, notation conventions, and repository scaffold, then validate a minimal end-to-end build.
>
> If you have direct access to the repository, modify and validate it directly. If you do not, use the playbook's patch/file handoff workflow.

---

# 25. Meta-principle

The finished work should feel as though it was **designed as a coherent book**, not accumulated as a sequence of individually competent answers.

That means consistency across the whole manuscript matters as much as local quality:

- terminology,
- notation,
- pacing,
- assumptions,
- visual language,
- cross-references,
- depth,
- citation standards,
- and pedagogy.

Whole-book coherence should be treated as a first-class engineering and editorial requirement.
