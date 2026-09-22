# Tramontina workshop schema (frozen)

**Status:** updated 2026-09-21 — short **3-letter codes** for folders; **long public slugs** on Vercel for participants.  
**Reference:** `themes/gty/`

Companion: [`../AUTHORING.md`](../AUTHORING.md) · [`../PROGRAM.md`](../PROGRAM.md).

---

## 1. Naming

| Layer | Rule | Example |
| --- | --- | --- |
| **Folder code** | Exactly **3 letters** under `themes/` | `gty`, `tcm`, `hwf` |
| **Public slug (Vercel)** | Long workshop name in the URL | `/negociacion-tactica/` |
| **Commercial title** | Human name on landings / README | Negociación Táctica y Empresarial |
| **Cierre** | `themes/cierre/{jul\|oct\|feb}/` · public `/cierre/…` | JUL / OCT / FEB |

No root aliases. You browse `themes/gty/`; participants open `/negociacion-tactica/`.

| Code | Public slug |
| --- | --- |
| `gty` | `negociacion-tactica` |
| `tcm` | `adaptabilidad-operativa` |
| `hwf` | `how-to-win-friends` |

---

## 2. One workshop = one folder

```text
themes/{code}/                 # e.g. gty
  README.md                    # commercial title + public slug
  index.html                   # INSTRUCTOR hub (noindex)
  _source/
  group-a|b/
    leadership-session/
    coaching-session/speaking/
```

---

## 3. README (required)

```markdown
# {CODE}
**Commercial title (participants):** …
**Public slug:** /{long-slug}/
```

---

## 4. Instructor hub UX

| Control | Target |
| --- | --- |
| **Abrir** | Local file under `themes/{code}/` (`facilitador.html`, etc.) |
| **Copiar** | Absolute **public** path (`/negociacion-tactica/group-a/leadership-session/`) |

Never Abrir a bare directory.

---

## 5. URLs

| Audience | Pattern |
| --- | --- |
| Builder / instructor | `themes/{code}/` (and `/themes/{code}/` on the site) |
| Participants | `/{public-slug}/group-{a\|b}/leadership-session/` |
| Cierre | `/cierre/jul/` etc. |

`vercel.json` **rewrites** public slugs → `themes/{code}/` (URL bar keeps the long name). Short codes `/gty/…` redirect to the long slug.

---

## 6. Cierre

Every **3** workshops → one close: `jul` / `oct` / `feb`.

---

## 7. Speaking

Under `coaching-session/speaking/`; method from repo `global_speaker/`.

---

## 8. Checklist

- [ ] Folder is 3-letter code under `themes/`
- [ ] README has commercial title + public slug
- [ ] Hub Copiar uses absolute public paths
- [ ] `vercel.json` rewrite for the public slug
- [ ] `_source/SHARE-URLS.md` updated
- [ ] Notes only in `_source/`
