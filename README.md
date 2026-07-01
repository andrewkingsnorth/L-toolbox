# LABDA Toolbox — landing page

The public landing page for the **LABDA Toolbox**: a curated, browsable catalog of the
code tools, methods and papers built by LABDA Fellows for movement behaviour analysis.
It's a **signpost** — every card links out to the live repository or DOI, nothing is
copied or hosted here.

Live site: `https://<org>.github.io/<repo>/`

---

## Updating the catalog (no coding needed)

All content lives in two spreadsheets. **Edit them and commit — the site updates itself.**
You do not need to touch `index.html`.

| File | Holds |
|------|-------|
| `tools.csv`  | Code tool cards |
| `papers.csv` | Paper / guidance cards |

You can edit these in Excel, Google Sheets, or directly in GitHub
(open the file → pencil icon → **Edit**). To **add** an entry, add a row; to **remove**
one, delete its row.

### `tools.csv` columns

| Column | Required | Notes |
|--------|----------|-------|
| `stage` | ✓ | Pipeline stage number: `1`, `2`, `3`, `6`, `8`, or `9` — decides which section the card appears in |
| `name` | ✓ | Tool name (card title) |
| `lang` | | Language shown on the card, e.g. `Python`, `R` |
| `repo` | ✓ | Link to the repository (the title links here) |
| `desc` | ✓ | Short description, 1–2 sentences |
| `contact` | ✓ | Contact person |
| `problem` | | "Problem it solves" (shown in the detail panel) |
| `whenToUse` | | "When to use it" |
| `needs` | | "What you need", e.g. `Python 3.9+, NumPy` |
| `outputs` | | "Outputs" |

### `papers.csv` columns

| Column | Required | Notes |
|--------|----------|-------|
| `stage` | ✓ | Pipeline stage number: `1`, `2`, `3`, `6`, `8`, or `9` |
| `title` | ✓ | Paper / guidance title (card title) |
| `kind` | | Badge label, e.g. `Protocol`, `Methods review`, `Guidance` |
| `url` | ✓ | Link to the DOI or resource (the title links here) |
| `summary` | ✓ | Plain-language summary, 1–2 sentences |
| `authors` | ✓ | Author(s) shown on the card |
| `contact` | ✓ | Contact person (shown in the detail panel) |
| `howToUse` | | "How to use it" |
| `why` | | "Why it is useful" |
| `targetUsers` | | Multiple values separated by `\|`, e.g. `Researchers\|Policy makers` |
| `example` | | "Example use case" |
| `limitations` | | "Limitations" |

**Tips**
- The pipeline stages are fixed (`1, 2, 3, 6, 8, 9`). A row whose `stage` doesn't match
  one of these won't appear.
- Fields containing commas are wrapped in double quotes — spreadsheet apps do this
  automatically, so just type normally.
- All content is public (it's shown on the page and served as plain files). Don't put
  anything you wouldn't publish into the CSVs.

---

## Publishing with GitHub Pages

1. Put `index.html`, `tools.csv` and `papers.csv` in the repository (root, together).
2. **Settings → Pages → Build and deployment → Source → Deploy from a branch.**
3. Choose branch `main` and folder `/ (root)`, then **Save**.
4. After ~1 minute the site is live at `https://<org>.github.io/<repo>/`.

The three files must stay in the same folder — the page loads the two CSVs relative to
`index.html`.

> **Note:** the site must be viewed over http(s) (GitHub Pages does this). Opening
> `index.html` directly from your computer will show built-in placeholder data instead
> of the CSVs, because browsers block reading local files — this does not affect the
> published site.

---

## Changing the design

`index.html` is a **compiled** file — don't hand-edit it. The design is maintained
separately and re-exported to `index.html` when it changes. Day-to-day catalog updates
only ever need the two CSV files above.
