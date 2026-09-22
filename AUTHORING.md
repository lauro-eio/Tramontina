# Authoring — Tramontina themes

Program math: [`PROGRAM.md`](PROGRAM.md).  
**Frozen schema:** [`themes/WORKSHOP-SCHEMA.md`](themes/WORKSHOP-SCHEMA.md).

## Locked conventions

- **Folders:** 3-letter codes under `themes/` (`gty`, `tcm`, `hwf`) — what you manage day to day
- **Public URLs:** long slugs on Vercel (`/negociacion-tactica/…`) — what participants get
- **No root aliases** — open hubs via `/` → `themes/gty/` or `/themes/gty/`
- **Cierre:** `themes/cierre/{jul|oct|feb}/`
- Structure: `{code} → group-a|b → leadership-session | coaching-session` (`speaking/` under coaching)

### Public slug map

| Code | Public slug |
| --- | --- |
| gty | `/negociacion-tactica/` |
| tcm | `/adaptabilidad-operativa/` |
| hwf | `/how-to-win-friends/` |

### Instructor hub UX

| Control | Target |
| --- | --- |
| **Abrir** | Local `facilitador.html` / deck / role-play |
| **Copiar** | Absolute public path, e.g. `/negociacion-tactica/group-a/leadership-session/` |

### Notes

Only under `themes/{code}/_source/`. Do not deploy `_source/` or `data/`.

## Start a new theme

1. Copy `themes/_template/` → `themes/{code}/` (3 letters).
2. Set commercial title + **public slug** in README.
3. Add Vercel rewrite: `/{public-slug}/:path*` → `/themes/{code}/:path*`.
4. Wire hub Copiar to absolute public paths.
5. Update SHARE-URLS + root thin hub.

## Patterns to copy

| Need | Copy from |
| --- | --- |
| Full workshop + hub | `themes/gty/` |
| Leadership hybrid | `themes/gty/group-b/leadership-session/` |
| Leadership interfuncional | `themes/gty/group-a/leadership-session/` |
| Coaching + PY | `themes/gty/group-a/coaching-session/` |
| Dual-group leadership | `themes/tcm/group-{a,b}/leadership-session/` |
| Cierre month | `themes/cierre/jul/` |

## Do not

- Put workshop folders at repo root
- Commit `data/`
- Put notes next to shipped HTML
- Copiar relative paths for participant landings (always use the public slug)
