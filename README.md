# Artificial Intelligence Fundamentals: Lecture Notes

Typeset lecture notes for **Artificial Intelligence Fundamentals**, University of
Pisa, academic year 2026/27. These notes are at an early stage: the folder is
scaffolded and builds, with content added lecture by lecture.

> ⚠️ **Disclaimer.** Derived from the *Artificial Intelligence Fundamentals*
> course materials (Academic Year 2026/2027), MSc in Data Science & Business
> Informatics, University of Pisa.
>
> These notes are open educational content created by a student. They are **not
> an academic source** and may contain inaccuracies. You may freely share,
> modify, and reuse this material for educational and non-commercial purposes
> with appropriate attribution. The content is my personal interpretation of the
> professor's course materials and should not replace official teaching
> resources. I assume no responsibility for any errors or misinterpretations.
>
> These notes were produced with an **AI-in-the-middle** workflow: a first human
> pass, then **Claude Code** to support formulation, understanding, and
> rewriting, followed by a final human review.
>
> If you find errors, have suggestions, or spot unintentionally included
> copyrighted material (which I will promptly remove on notification), contact me
> at `sclfnc@proton.me`.

This course is part of the [MSc Data Science lecture notes](https://github.com/sclfnc/unipi-ds-notes) collection (University of Pisa), one repository per course. Clone the whole set with `git clone --recursive`.

## Layout

- `main.tex`: entry point, in the folder root; identical across the whole
  notes collection (it only loads the shared preamble and the course file).
- `src/housestyle.tex`, shared house style: geometry, colors, section and ToC
  formatting, running heads, and the math environments (theorem, definition, …).
- `src/common-preamble.tex`: the shared package set, identical across courses.
- `src/course.tex`, everything specific to this course: title metadata, math
  macros, the house callouts, `hyperref`/`cleveref`, the bibliography resource,
  and the `\input{sec/...}` list.
- `sec/_NN_*.tex`: section files (the body of the notes), pulled in by `course.tex`.
- `references.bib`: bibliography (biblatex / Biber, numeric style).
- `aif-notes.pdf`: the compiled notes, in the folder root.

## Build

The notes use `biblatex` with the Biber backend and `cleveref` (which needs a
final pass for cross-references). Build from the folder root:

```bash
latexmk main.tex
```

`latexmk` runs pdflatex and Biber as many times as needed. The compiled PDF is
named `aif-notes.pdf`; the LaTeX auxiliaries (`.aux`, `.log`, `.toc`, `.bcf`,
`.bbl`, …) land in the folder root alongside it and are git-ignored (listed in
`.gitignore`). A `.latexmkrc` in the folder sets this up (it also renames the
output via `$jobname`). To do it by hand instead:

```bash
pdflatex -jobname=aif-notes main && biber aif-notes && pdflatex -jobname=aif-notes main && pdflatex -jobname=aif-notes main
```

Requires a standard TeX Live installation. Alternatively, upload the folder to
[Overleaf](https://www.overleaf.com) (New Project → Upload Project), set
`main.tex` as the main document, and compile.

## Credits

Written by **Francesco Secoli**, revised with the help of
[Claude Code](https://claude.com/claude-code): the course slides and lectures
were transcribed and refined into LaTeX, then reworked into standalone notes.
Based on the *Artificial Intelligence Fundamentals* course (a.y. 2026/27),
University of Pisa. Contributions welcome: open an issue or a pull request.
