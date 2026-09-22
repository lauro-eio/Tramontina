# Instructor share URLs

Schema: [`themes/WORKSHOP-SCHEMA.md`](../themes/WORKSHOP-SCHEMA.md).

## Instructor hubs (short codes)

| Code | Commercial title | Hub |
| --- | --- | --- |
| — | Thin directory | `/` |
| gty | Negociación Táctica y Empresarial | `/themes/gty/` |
| tcm | Adaptabilidad Operativa | `/themes/tcm/` |
| hwf | How to Win Friends — Operación Salvavidas | `/themes/hwf/` |
| cierre | Cierre de ciclo | `/themes/cierre/` |

## Participant landings (public long slugs)

| Code | Group | Public URL |
| --- | --- | --- |
| gty | A leadership | `/negociacion-tactica/group-a/leadership-session/` |
| gty | B leadership | `/negociacion-tactica/group-b/leadership-session/` |
| tcm | A leadership | `/adaptabilidad-operativa/group-a/leadership-session/` |
| tcm | B leadership | `/adaptabilidad-operativa/group-b/leadership-session/` |
| hwf | B leadership | `/how-to-win-friends/group-b/leadership-session/` |
| cierre | JUL | `/cierre/jul/` |

## Hub UX

**Abrir** → local `facilitador.html` · **Copiar** → absolute public path · never Abrir a bare directory.

## Vercel

Rewrites map public slugs → `themes/{code}/`. Short `/gty/…` redirects to `/negociacion-tactica/…`.
