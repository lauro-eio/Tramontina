# Tramontina workshop schema (frozen)

**Status:** frozen 2026-09-21 after smoke-test of Negociación Táctica (`gty` / `negociacion-tactica`).  
**Reference implementation:** `themes/negociacion-tactica/`  
**Do not invent parallel layouts.** Copy `_template/` or clone this theme’s shape.

Companion: [`../AUTHORING.md`](../AUTHORING.md) · [`../PROGRAM.md`](../PROGRAM.md).

---

## 1. One workshop = one folder

```text
themes/{theme-slug}/
  index.html                 # INSTRUCTOR hub (noindex) — ONLY entry for coaches
  README.md
  _source/                   # notes/briefs — not deployed
  group-a/
    leadership-session/      # 3h leadership package
    coaching-session/        # 3h skills day
      speaking/              # oratoria under coaching (from global_speaker)
  group-b/
    leadership-session/
    coaching-session/
      speaking/
```

Forbidden folder names in new work: `s1-leadership`, `s2-skills`.

---

## 2. Surfaces

| File | Audience | Abrir from instructor hub? |
| --- | --- | --- |
| `themes/{slug}/index.html` | Instructor | — (this is the hub) |
| `…/leadership-session/index.html` | **Participants** | Never as default Abrir |
| `…/facilitador.html` | Instructor | **Yes — default Abrir for Leadership / Coaching** |
| `…/role-play.html` | Instructor (paste in chat) | Yes |
| `…/deck/session*.html` | Instructor (project) | Yes — link the **HTML file**, not `deck/` |
| Root `/index.html` | Instructor | Thin directory of workshops only |

---

## 3. Instructor hub UX (locked)

On `themes/{slug}/index.html`:

| Row | **Abrir** | **Copiar** |
| --- | --- | --- |
| Leadership | `…/leadership-session/facilitador.html` | `…/leadership-session/` (participant URL) |
| Role-play | `…/role-play.html` | same path |
| Deck | `…/deck/session-01.html` (or whatever file exists) | same file path |
| Coaching | `…/coaching-session/facilitador.html` | `…/coaching-session/` |

**Never** set Abrir `href` to a bare directory (avoids local folder listings of README / qr).

Omit rows for packages that are not built yet (show “Not built”).

---

## 4. URLs

| Audience | Pattern |
| --- | --- |
| Participants | `/{theme-slug}/group-{a\|b}/leadership-session/` (workshop **name** in path) |
| Instructor hub | `/{theme-slug}/` or opaque alias (`/gty/`, `/tcm/`, `/hwf/`) pointing at the **same theme tree** |
| Legacy opaque deep links | `vercel.json` redirects → `/{theme-slug}/group-…/leadership-session/…` |

Root aliases: `negociacion-tactica`, `adaptabilidad-operativa`, `how-to-win-friends` → `themes/{slug}`.  
Opaque: `gty`, `tcm`, `hwf` → same theme trees (instructor convenience).

Edit content under `themes/` only — not via alias paths in the IDE when avoidable.

---

## 5. Speaking

Lives at `coaching-session/speaking/`. Method/content adapted from repo `global_speaker/`.

---

## 6. Checklist — new or migrated theme

- [ ] Folders renamed to `leadership-session` / `coaching-session` (+ `speaking/`)
- [ ] Theme `index.html` instructor hub follows §3 Abrir/Copiar rules
- [ ] Root thin hub links to this theme’s instructor index
- [ ] Participant-friendly symlink `/{theme-slug}` → `themes/{theme-slug}`
- [ ] Opaque alias updated if one exists; `vercel.json` legacy redirects
- [ ] `_source/SHARE-URLS.md` + theme `README.md` updated
- [ ] No notes sitting next to shipped HTML

---

## 7. Reference

Smoke-tested hub: [`negociacion-tactica/index.html`](negociacion-tactica/index.html).
