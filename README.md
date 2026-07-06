# LABDA Toolbox — landing page

The public landing page for the **LABDA Toolbox**: a curated, browsable catalog of the
code tools and resources built by LABDA Fellows for movement behaviour analysis.
It's a **signpost** — every card links out to the live repository or paper, nothing is
copied or hosted here.

Live site: `https://<org>.github.io/<repo>/`

---

## Updating the catalog (no coding needed)

All content lives in **one file: `tools.csv`**. Edit it and commit — the site updates
itself. You do not need to touch the page itself.

You can edit `tools.csv` in Excel, Google Sheets, or directly in GitHub
(open the file → pencil icon → **Edit**). To **add** a card, add a row; to **remove**
one, delete its row.

### `tools.csv` columns

| Column | Required | Notes |
|--------|----------|-------|
| `type` | ✓ | `code` or `resource` — decides which section the card appears in (green **Code Tools** or teal **Resources**) |
| `title` | ✓ | Card title (e.g. the tool name or paper title) |
| `tagline` | ✓ | Short one-line description shown on the card |
| `author` | ✓ | Author or contact shown on the card |
| `description` | ✓ | Longer detail shown in the pop-out panel when a card is clicked |
| `intendedUser` | | Who it's for. Multiple values separated by `\|`, e.g. `Researchers\|Policy makers` |
| `tags` | | Free-text keywords. Multiple values separated by `\|`, e.g. `signal-processing\|Python` |
| `link` | ✓ | Link to the repository or paper (the title and buttons link here) |

**How the fields show up**
- **title**, **tagline** and **author** appear on the card tile.
- **description**, **intendedUser** and **tags** all appear in the detail panel (tags and
  intended-user chips also show on the card).
- **type** = `code` gives the card the green terminal-style header; anything else is
  treated as a `resource` (teal).

**Tips**
- Fields containing commas are wrapped in double quotes — spreadsheet apps do this
  automatically, so just type normally.
- `intendedUser` and `tags` are **pipe-separated** (`|`) — each value becomes its own chip.
- All content is public (it's shown on the page and served as a plain file). Don't put
  anything you wouldn't publish into the CSV.

---

## Publishing with GitHub Pages

1. Put the page file and `tools.csv` in the repository (root, together).
2. **Settings → Pages → Build and deployment → Source → Deploy from a branch.**
3. Choose branch `main` and folder `/ (root)`, then **Save**.
4. After ~1 minute the site is live at `https://<org>.github.io/<repo>/`.

The files must stay in the same folder — the page loads `tools.csv` relative to itself.

> **Note:** the site must be viewed over http(s) (GitHub Pages does this). Opening the
> page directly from your computer will show built-in placeholder data instead of the
> CSV, because browsers block reading local files — this does not affect the published
> site.

---

## Changing the design

The page is a **compiled** file — don't hand-edit it. The design is maintained separately
and re-exported when it changes. Day-to-day catalog updates only ever need `tools.csv`.
