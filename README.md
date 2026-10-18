# Obsidian Lined Paper

Two CSS snippets that turn Obsidian notes into handwritten notebook pages, with an optional Cornell notes layout.

- **Lined paper:** ruled lines, a red margin, handwriting fonts, a pinned title bar, and a date in the corner. Text sits on the lines.
- **Cornell notes:** a cue column, a notes column, and a summary box pinned to the bottom of the page.
- Light and dark themes.
- Opt-in per note. Notes without the class look exactly as before.

<!-- Add screenshots here: docs/lined-paper.png, docs/cornell.png -->

## Install

1. Copy the files in `snippets/` to `<your vault>/.obsidian/snippets/`.
2. In Obsidian, open **Settings → Appearance → CSS snippets** and turn on `lined-paper` (and `cornell-notes` if you want it).

## Use

Add a class to a note's properties:

```yaml
---
cssclasses: lined-paper
date: 2026-10-18
---
```

The first `# Heading` becomes the title bar. The `date` property (type: Date) appears in its top-right corner. All other properties are hidden on these notes.

### Cornell notes

Use both classes:

```yaml
---
cssclasses: [lined-paper, cornell]
---
```

Then write plain callouts, with a blank line between each:

```markdown
> [!cue]
> What goes in?

> [!notes]
> Light, water and carbon dioxide.

> [!summary] Summary
> One short paragraph, last in the note.
```

The Cornell layout appears in **Reading view**. In the editor you see ordinary lined paper.

See [`examples/`](examples) for ready-to-copy notes.

## Customise

Settings are CSS variables at the top of each file.

| Variable | Default | What it does |
| --- | --- | --- |
| `--line` | `36px` | Height of one ruled line |
| `--text` | `22px` | Body text size |
| `--title` | `46px` | Title size |
| `--bar-lines` | `3` | Title bar height, in lines |
| `--pad-x` | `76px` | Left and right page padding |
| `--paper`, `--rule`, `--margin`, `--ink` | see file | Page, ruling, margin line and text colours |
| `--cue` | `0.3` | Cue column width (Cornell) |
| `--cue-ink` | `#2b5aa8` | Cue pen colour (Cornell). Use `var(--ink)` for one pen |
| `--summary-lines` | `5` | Summary box height in lines (Cornell) |
| `--label-cue`, `--label-notes` | `"Cues"`, `"Notes"` | Column labels (Cornell) |

To change a value for one theme only, override it under `.theme-dark .lined-paper { ... }`.

## Notes

- The fonts (Patrick Hand and Caveat) load from Google Fonts. Offline, system handwriting fonts are used instead.
- The snippets size everything in whole ruled lines. If you change `--line`, change `--text` to keep it readable.
- Plugins that restyle headings, callouts or properties may conflict.

## License

[MIT](LICENSE)
