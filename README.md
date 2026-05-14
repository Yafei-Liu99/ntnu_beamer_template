# NTNU Beamer Template

A clean, NTNU-branded LaTeX Beamer template for lectures and presentations. Features automatic section navigation, speaker notes support, and a consistent color scheme based on NTNU's visual identity.

## Quick Start

1. **Clone this repository** (or import into Overleaf):
   ```bash
   git clone https://github.com/Yafei-Liu99/ntnu_beamer_template.git
   ```

2. **Edit `slide.tex`** — replace the placeholder content with your own:
   ```latex
   \author[Author]{Your Name}
   \title[Lecture Title]{Lecture Title Here}
   \subtitle{Course Name --- Lecture N}
   \institute[NTNU]{Department of Economics, NTNU}
   ```

3. **Compile**:
   ```bash
   pdflatex slide.tex
   pdflatex slide.tex   # run twice for navigation links
   ```

## Files

| File | Description |
|------|-------------|
| `slide.tex` | Main presentation (no speaker notes) |
| `slide_notes.tex` | Presentation with speaker notes (use with [pympress](https://github.com/Cimbali/pympress)) |
| `NTNU.sty` | Style package — colors, layout, navigation bar, custom commands |
| `ref.bib` | Bibliography template |
| `pic/` | NTNU logo and background assets |

## Features

### Autoframe Navigation

Use `\begin{autoframe}{Title}` instead of `\begin{frame}{Title}` to get automatic dot-navigation in the headline bar. The dots track your position within each subsection.

```latex
\subsection{My Subsection}

\begin{autoframe}{Slide Title}
    Your content here.
\end{autoframe}
```

Regular `\begin{frame}` still works for special slides (title page, outline, etc.).

### Section Intro Pages

Each `\section{}` automatically generates a centered section title slide — no extra code needed.

### Timeline

Built-in timeline command for showing project phases or lecture schedules:

```latex
\timeline{3}{%                              % 3 = highlight the 3rd phase
    {Sep--Dec 2025}/{Literature review},
    {Jan--Mar 2026}/{Model development},
    {Apr--Jun 2026}/{Empirical analysis},    % ← highlighted
    {Jul--Sep 2026}/{Writing},
    {Oct--Dec 2026}/{Submission}%
}
```

### Thank-You Page

```latex
\makethankyou[your.email@ntnu.no]    % email is optional
```

### Blocks

Three block styles with increasing emphasis:

```latex
\begin{exampleblock}{Soft}       ... \end{exampleblock}   % lightest
\begin{block}{Standard}          ... \end{block}           % medium
\begin{alertblock}{Important}    ... \end{alertblock}      % strongest
```

### Speaker Notes

`slide_notes.tex` includes `\note{}` blocks after each frame with suggested talking points. Compile it and present with [pympress](https://github.com/Cimbali/pympress) for dual-screen output (slides on projector, notes on your laptop).

## Color Palette

| Color | RGB | Usage |
|-------|-----|-------|
| `ntnusky` | (221, 231, 238) | Headline bar, block backgrounds |
| `ntnublue` | (0, 80, 158) | Frame titles, structure elements |
| `ntnudark` | (0, 56, 112) | Footline, alert blocks |

## Using with Overleaf

Import this repository directly into Overleaf via **New Project > Import from GitHub**, or clone the Overleaf project:

```bash
git clone https://git.overleaf.com/6a03758cfdc17ed26a51951c
```

## Template Examples

The appendix of `slide.tex` includes ready-to-use examples:

- Incremental reveal (overlay)
- Block types
- Timeline
- Tables
- Equations
- Two-column layout

## License

Free to use for NTNU teaching and research.
