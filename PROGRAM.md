# Tramontina Monthly Leadership Program (9 Modules)

1 company · 2 groups · 9 themes · **12 facilitator hours / month** (6h × 2 groups).

Folder and URL rules: [`AUTHORING.md`](AUTHORING.md) (**locked conventions**).

## Monthly structure (1 theme = 1 month)

```
                        MONTHLY THEME (1 of 9)
                                  │
         ┌────────────────────────┴────────────────────────┐
         ▼                                                 ▼
      GROUP A                                           GROUP B
 (Supporting Areas)                                  (Sales Team)
     6 Hours                                           6 Hours
         │                                                 │
 ┌───────┴───────┐                                 ┌───────┴───────┐
 ▼               ▼                                 ▼               ▼
leadership-    coaching-                         leadership-    coaching-
 session        session                           session        session
  (3h)           (3h)                              (3h)           (3h)
```

### leadership-session (3h)

- Whole group (A or B)
- Theme principles and framework

### coaching-session (3h)

Group splits into two subgroups (A1/A2 or B1/B2). Speaking lives under the coaching tree; method from `global_speaker/`.

| Time block | Subgroup 1 | Subgroup 2 |
| --- | --- | --- |
| Block 1 (1.5h) | Coaching (PrinciplesYou) | Speaking |
| Block 2 (1.5h) | Speaking | Coaching (PrinciplesYou) |

## Folder rule (canonical)

```text
themes/{theme-slug}/
  index.html                 # instructor only — this workshop
  README.md
  _source/                   # briefs / notes — not deployed
  group-a/
    leadership-session/
    coaching-session/
      speaking/
  group-b/
    leadership-session/
    coaching-session/
      speaking/
```

Copy [`themes/_template/`](themes/_template/) when starting a new theme.

**Participant shares:** path includes the theme slug (workshop name), e.g. `/themes/negociacion-tactica/group-a/leadership-session/`.

**Opaque codes** (`gty`, `tcm`, `hwf`): instructor / legacy only — see [`_source/SHARE-URLS.md`](_source/SHARE-URLS.md).

Root [`index.html`](index.html) is a **thin** workshop directory, not a second fat instructor runbook.
