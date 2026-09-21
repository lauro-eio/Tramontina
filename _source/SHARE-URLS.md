# Instructor share URLs (Vercel)

Canonical schema: [`themes/WORKSHOP-SCHEMA.md`](../themes/WORKSHOP-SCHEMA.md).

## Instructor hubs

| Workshop | Full name | Opaque |
| --- | --- | --- |
| Thin directory (all) | `/` | — |
| Negociación Táctica | `/negociacion-tactica/` | `/gty/` |
| Adaptabilidad Operativa | `/adaptabilidad-operativa/` | `/tcm/` |
| How to Win Friends | `/how-to-win-friends/` | `/hwf/` |
| Cierre (examples) | `/cierre/` | — |

## Participant landings (share these — workshop name in path)

| Theme | Group | Session | URL |
| --- | --- | --- | --- |
| Negociación Táctica | A | leadership | `/negociacion-tactica/group-a/leadership-session/` |
| Negociación Táctica | B | leadership | `/negociacion-tactica/group-b/leadership-session/` |
| Adaptabilidad Operativa | A | leadership | `/adaptabilidad-operativa/group-a/leadership-session/` |
| Adaptabilidad Operativa | B | leadership | `/adaptabilidad-operativa/group-b/leadership-session/` |
| How to Win Friends | B | leadership | `/how-to-win-friends/group-b/leadership-session/` |

Role-play (coach paste):

- GTY A/B: `/negociacion-tactica/group-{a\|b}/leadership-session/role-play.html`
- TCM A/B: `/adaptabilidad-operativa/group-{a\|b}/leadership-session/role-play.html`

## Hub UX reminder

**Abrir** → `facilitador.html` (or role-play / deck **file**). **Copiar** → participant folder URL. Never Abrir a bare directory.

## Legacy

`vercel.json` redirects old `/tcm/a`, `/tcm/b`, `/tcm-a`, `/gty/a`, `/gty/b`, flat `/gty/*.html`, `/hwf/facilitador.html` into the paths above.
