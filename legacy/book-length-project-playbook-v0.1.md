# Book-Length Project Playbook

**Purpose:** Reusable starting context for technical or scholarly book-length projects developed collaboratively with ChatGPT.

**Status:** Draft v0.1 — intended to be refined over time.

---

## 1. What this document is for

This document defines a reusable working method for producing rigorous, polished, book-length technical or scholarly works.

It is intended to preserve the decisions that otherwise tend to be rediscovered through repeated prompting:

- editorial and pedagogical style,
- mathematical and citation conventions,
- repository organization,
- manuscript/build workflow,
- figure standards,
- exercise and workbook conventions,
- quality-control and release procedures,
- and the expected collaboration pattern between author and AI.

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

---

# 3. Editorial principles

## 3.1 Explain before compressing

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

## 3.2 Distinguish levels of claim

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

## 3.3 Preserve nuance

Do not force superficially similar concepts into a stronger unification than the mathematics or literature supports.

When several fields use similar mathematical structures, distinguish:

1. formal mathematical equivalence,
2. interpretive or statistical relationship,
3. operational or physical relationship.

This distinction is often important in interdisciplinary books.

## 3.4 Avoid false simplification

Prefer:

> "A useful intuition is..."

over:

> "X is just..."

when the latter would erase important structure.

Avoid textbook clichés that are pedagogically familiar but technically misleading.

## 3.5 Derivations should show the important steps

Do not skip algebraic or conceptual steps that a motivated non-specialist reader is likely to wonder about.

A good derivation should make clear:

- what is being substituted,
- which identity or theorem is being used,
- why a rearrangement is legal,
- where an assumption enters,
- and what the resulting expression means.

Routine arithmetic may be compressed; non-obvious transformations should not be.

## 3.6 Historical material should explain conceptual development

History is most valuable when it explains:

- what problem motivated a concept,
- what earlier formulation was insufficient,
- how the modern formulation changed the field,
- which distinctions emerged later.

Avoid decorative name-and-date lists.

---

# 4. Chapter architecture

Chapters need not be mechanically identical, but the following pattern is a strong default.

## 4.1 Opening

Each chapter should establish:

- the problem or question,
- why it matters,
- what the reader should learn,
- how it connects to earlier chapters.

## 4.2 Conceptual development

Introduce the main idea informally before relying on dense notation where possible.

## 4.3 Formal development

Definitions, propositions, derivations, and equations should follow naturally from the conceptual setup.

## 4.4 Examples

Use examples that illuminate structure rather than merely substitute numbers into formulas.

Prefer examples that expose:

- edge cases,
- counterintuitive behavior,
- common errors,
- practical consequences.

## 4.5 Connections

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

## 4.6 Chapter close

A short synthesis is useful when a chapter contains several conceptual layers.

The closing should emphasize what changed in the reader's understanding rather than simply recapitulating headings.

---

# 5. Exercises

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

# 6. Companion hints-and-solutions workbook

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

# 7. Mathematical typesetting

## 7.1 Source format

Markdown is the canonical manuscript source unless there is a strong project-specific reason to use another format.

Use LaTeX syntax for mathematics.

## 7.2 Inline mathematics

Use:

```text
$...$
```

for short inline expressions.

## 7.3 Display mathematics

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

## 7.4 Compatibility

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

## 7.5 Notation discipline

Maintain a notation glossary for books with substantial mathematics.

Notation should be:

- introduced before use,
- consistent across chapters,
- reused rather than reinvented,
- and checked globally before release.

---

# 8. Citations and bibliography

Use a project-level BibTeX file, normally:

```text
references.bib
```

Use citation keys consistently in the Markdown source.

## 8.1 Source hierarchy

Prefer, roughly:

1. original primary papers for foundational results,
2. authoritative monographs or textbooks,
3. high-quality review papers,
4. institutional or professional sources,
5. secondary explanatory sources only where appropriate.

## 8.2 Citation placement

Citations should support meaningful factual, historical, or research claims.

Do not cite every sentence mechanically.

Do cite:

- historical priority,
- empirical claims,
- contested interpretations,
- named results,
- modern research claims,
- specific technical developments.

## 8.3 Final bibliography checks

Before release:

- verify that every citation key resolves,
- identify unused bibliography entries,
- inspect formatting,
- and spot-check important references manually.

---

# 9. Figures

Figures should be treated as publication assets, not incidental plotting output.

## 9.1 Goals

A figure should:

- explain something that prose alone explains less efficiently,
- have clear visual hierarchy,
- remain legible in print,
- use consistent typography,
- use restrained color,
- avoid gratuitous decoration,
- and visually match the quality of the manuscript.

## 9.2 Figure classes

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

## 9.3 Curated publication assets

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

## 9.4 Figure references

Figure paths in chapter Markdown should work both on GitHub and during PDF generation.

The PDF build should use resource paths rather than requiring source paths to be rewritten.

---

# 10. Repository structure

A good default repository layout is:

```text
/
├── README.md
├── STYLE_GUIDE.md
├── LICENSE.md
├── book.md
├── metadata.yaml
├── references.bib
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

---

# 11. Build system

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

## 11.1 Python environment

Use:

```bash
uv sync
```

and run project Python tools with:

```bash
uv run python ...
```

Avoid requiring manual virtual-environment activation.

## 11.2 Main PDF build

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

## 11.3 Workbook build

The companion workbook should have a separate build target.

## 11.4 Builds should not mutate source assets

A normal book build must not:

- rewrite manuscript Markdown,
- regenerate curated figures,
- update lockfiles,
- or modify committed source files.

Build outputs belong in `output/`.

---

# 12. Repository checks

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

# 13. Indexing

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

# 14. PDF typography and layout

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

# 15. Cross-platform considerations

Assume the project may be developed on Windows while using Git Bash.

Avoid platform-fragile assumptions.

Important practices:

- explicit UTF-8 file I/O in Python,
- Windows-safe shell scripts,
- PowerShell alternatives where useful,
- no unnecessary executable-bit churn,
- correct path separator handling for Pandoc resource paths,
- no dependence on a GUI tool when command-line tooling is sufficient.

---

# 16. Git and patch workflow

The user's repository is canonical.

When collaborating through generated patches:

1. assume the latest pushed repository state is authoritative,
2. make narrow patches,
3. avoid unrelated file churn,
4. avoid modifying frequently drifting files unless necessary,
5. avoid binary patches when binary files may have been regenerated locally.

Recommended user workflow:

```bash
git pull --rebase
git apply --check /c/Users/<user>/Downloads/change.patch
git apply /c/Users/<user>/Downloads/change.patch
```

Then validate before committing.

For binary publication assets, prefer:

- a source-only patch for code/configuration changes,
- plus an archive of replacement assets,

rather than a Git binary patch whose hashes are likely to fail.

---

# 17. Collaboration workflow with ChatGPT

This section is especially important.

## 17.1 Work from artifacts, not summaries alone

Once a repository exists, the actual files should be treated as authoritative.

Do not reconstruct chapters or configuration from memory if current files are available.

## 17.2 Prefer implementation over repeated planning

When the direction is clear, move directly to:

- drafting,
- editing,
- validating,
- building,
- or producing the patch.

Avoid repeatedly restating the intended plan without making progress.

## 17.3 Preserve agreed decisions

Once an editorial or architectural choice is settled, treat it as a project convention until explicitly changed.

Do not re-litigate established decisions casually.

## 17.4 Separate conceptual review from mechanical editing

For major revisions, distinguish:

- substantive conceptual problems,
- pedagogical improvements,
- stylistic copy edits,
- mechanical formatting changes.

This makes review easier and reduces accidental regressions.

## 17.5 Make changes incrementally

Large books should be developed in reviewable increments.

Good units include:

- one chapter,
- a small group of chapters,
- one figure pass,
- one exercise pass,
- one indexing pass,
- one final copy-edit pass.

## 17.6 Test patches before handoff

Before providing a patch:

- apply it to a clean copy of the expected baseline,
- run relevant validation,
- ensure paths are repository-relative,
- and avoid binary patching where baseline hashes are uncertain.

## 17.7 Own baseline mismatches

If a patch fails because the assumed baseline was wrong, diagnose the mismatch and generate a safer correction.

Do not force the user into complicated Git recovery merely to preserve an AI-generated patch.

---

# 18. Recommended project phases

A useful default lifecycle is:

## Phase 1 — Concept and scope

Develop:

- purpose,
- thesis or organizing framework,
- audience,
- prerequisites,
- scope,
- chapter architecture,
- research standard.

## Phase 2 — Repository scaffold

Create:

- directory structure,
- metadata,
- bibliography,
- style guide,
- build scripts,
- math validation,
- initial README.

Build a minimal PDF immediately.

## Phase 3 — Core manuscript

Draft chapters incrementally.

After each substantial group:

- build,
- inspect,
- revise,
- commit.

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

# 19. Final QA checklist

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
- [ ] License present.
- [ ] Version committed.
- [ ] Release tag points to intended commit.

---

# 20. Licensing default

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

# 21. Decisions that should remain project-specific

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

# 22. High-value defaults for future projects

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
14. Incremental patch-based collaboration.
15. Whole-manuscript revision before final copy edit.
16. Visual PDF inspection before release.
17. Release tags treated as immutable once published.

---

# 23. Suggested initial prompt for a future project

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
> Before drafting chapters, help me develop the organizing thesis, chapter architecture, and repository scaffold. Challenge weak assumptions or scope choices rather than merely accepting them.

---

# 24. Meta-principle

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
