# Authoring — Tramontina themes

How to create content for the next month. Program math: [`PROGRAM.md`](PROGRAM.md). Theme index: [`themes/README.md`](themes/README.md).

## Locked conventions (2026-09-21)

These are **canonical**. Full freeze: [`themes/WORKSHOP-SCHEMA.md`](themes/WORKSHOP-SCHEMA.md) (smoke-tested on Negociación Táctica).

Do not reintroduce `s1` / `s2` folder names or fat dual instructor hubs.

### Mental model

```text
theme (workshop) → group-a|group-b → leadership-session | coaching-session
```

| Term | Meaning |
| --- | --- |
| **Theme / workshop** | One monthly module (one folder under `themes/`) |
| **Group A / B** | Supporting Areas / Sales — parallel tracks, never share landings |
| **leadership-session** | 3h whole-group leadership (was “S1”) |
| **coaching-session** | 3h skills day: PrinciplesYou coaching + speaking rotation (was “S2”) |
| **speaking/** | Lives **under** `coaching-session/speaking/`; method from repo `global_speaker/`, adapted to the theme |

### Folder rule

```text
themes/{theme-slug}/
  index.html               # INSTRUCTOR ONLY (noindex) — this workshop’s runbook + share URLs
  README.md
  _source/                 # briefs, notes, plans — NOT deployed
  group-a/
    leadership-session/    # participant index.html + facilitador + role-play + deck + qr
    coaching-session/
      …                    # coaching / PrinciplesYou package
      speaking/            # oratoria block (Global Speaker → theme)
  group-b/
    leadership-session/
    coaching-session/
      speaking/
```

### Instructor vs participant surfaces

| Surface | What | URL style |
| --- | --- | --- |
| **Theme `index.html`** | Instructor hub for **this workshop only** | Internal OK (`/themes/negociacion-tactica/` or opaque `/gty/`) |
| **Root `/index.html`** | **Thin** directory of workshops → each theme’s instructor index. Not a second fat runbook |
| **Session `index.html`** | Participant landing | **Full workshop name in path** (see below) |
| **`facilitador.html` / `role-play.html` / `deck/`** | Coach-only | May use opaque codes; never linked from participant landings |

### Participant URLs (preferred)

Use the **theme slug** (full workshop name), not opaque codes:

```text
/themes/negociacion-tactica/group-a/leadership-session/
/themes/negociacion-tactica/group-a/coaching-session/
```

Optional root alias (same tree): `/negociacion-tactica/group-a/leadership-session/` if a symlink exists.

Opaque codes (`gty`, `tcm`, `hwf`) are **instructor / legacy redirects only** — do not paste them to participants for new shares.

### Instructor hub UX (required)

On each theme `index.html`:

| Control | Target |
| --- | --- |
| **Abrir** Leadership / Coaching | `facilitador.html` (never a bare folder) |
| **Abrir** Role-play / Deck | the `.html` file (e.g. `deck/session-01.html`) |
| **Copiar** | participant folder URL (`…/leadership-session/`) |

See [`themes/WORKSHOP-SCHEMA.md`](themes/WORKSHOP-SCHEMA.md) §3.

### Participant landing filename

Keep **`index.html`** inside each session folder so the share URL is the folder path (no `landing.html` in the link).

### Notes and source

- Working notes, briefs, plans → `themes/{slug}/_source/` only
- Never leave notes next to shipped HTML (avoids “editing via `gty/` symlink” confusion)
- Do not deploy `_source/` or `data/` (`.vercelignore`)

### Speaking / Global Speaker

- Oratoria content is adapted from [`global_speaker/`](../../global_speaker/) (syllabus, framework, worksheets)
- Package it under `coaching-session/speaking/` for that group — not a sibling of `leadership-session`

## Start a new theme

1. Copy `themes/_template/` → `themes/{slug}/`.
2. Add a row in [`themes/README.md`](themes/README.md).
3. Write `_source/brief` (and notes) under the theme.
4. Build usually: B `leadership-session/` → A `leadership-session/` → each group’s `coaching-session/` (+ `speaking/`).
5. Wire Forms + `qr/`; fill **theme** `index.html` (instructor); update [`_source/SHARE-URLS.md`](_source/SHARE-URLS.md).
6. Root hub stays a thin link to this theme’s instructor index.
7. Opaque short codes only if needed for legacy instructor bookmarks — prefer theme-slug paths for participants.

## Deliverable matrix (per group × theme)

| Artifact | leadership-session | coaching-session | speaking/ (under coaching) |
| --- | --- | --- | --- |
| Participant `index.html` | required | optional short | optional short |
| `facilitador.html` (`noindex`) | required | required | required |
| `role-play.html` / lab | if simulation | if practice cases | if speech lab |
| `deck/session*.html` | preferred for 3h | optional 90′ | optional 90′ |
| Forms + `qr/` | as needed | as needed | as needed |
| PrinciplesYou / `data/` join | coach-only | often | rare |

## Patterns to copy

| Need | Copy from |
| --- | --- |
| Full workshop shape + instructor hub | `themes/negociacion-tactica/` + [`themes/WORKSHOP-SCHEMA.md`](themes/WORKSHOP-SCHEMA.md) |
| Leadership hybrid (landing + facilitador + role-play + deck) | `themes/negociacion-tactica/group-b/leadership-session/` |
| Leadership interfuncional (Grupo A) | `themes/negociacion-tactica/group-a/leadership-session/` |
| Coaching (90′ + PrinciplesYou) | `themes/negociacion-tactica/group-a/coaching-session/` |
| Dual-group leadership (no deck) | `themes/adaptabilidad-operativa/group-{a,b}/leadership-session/` |
| Share / isolation rules | `_source/SHARE-URLS.md` |

## Do not

- Use folder names `s1-leadership`, `s2-skills` in new work
- Put coaching under the other group’s leadership folder
- Mix Group A and B averages or show individual PrinciplesYou scores on participant pages
- Deploy `data/` or `_source/`
- Treat opaque codes as the authoring mental model
- Maintain two fat instructor hubs (root + theme)
- Link role-play from participant landings
- Edit content through root alias folders (`gty/`, `tcm/`) — edit under `themes/`

## Migration status

| Theme | Schema |
| --- | --- |
| `negociacion-tactica` | Frozen reference |
| `adaptabilidad-operativa` | Migrated |
| `how-to-win-friends` | Migrated |
| `cierre` | Instructor index + examples (not full A/B) |
| `themes/_template` | Matches schema |

## Data

Roster and PrinciplesYou CSVs live in [`data/`](data/). Join on email. Filter by `Grupo` column before any projected aggregate.
