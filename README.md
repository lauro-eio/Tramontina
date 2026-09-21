# Tramontina

Instructor-facing static site (`lauro-eio/Tramontina`).

**Frozen schema:** [`themes/WORKSHOP-SCHEMA.md`](themes/WORKSHOP-SCHEMA.md)  
Also: [`AUTHORING.md`](AUTHORING.md) · [`PROGRAM.md`](PROGRAM.md) · [`_source/SHARE-URLS.md`](_source/SHARE-URLS.md)

## Layout

```text
themes/{slug}/
  index.html                # instructor hub (Abrir → facilitador)
  group-a|b/
    leadership-session/     # participant index.html
    coaching-session/speaking/
index.html                  # thin directory of workshops
{slug}/  gty|tcm|hwf/       # aliases → themes/{slug}
```

## Participant vs instructor

| Audience | Example |
| --- | --- |
| Participants | `/negociacion-tactica/group-a/leadership-session/` |
| Instructor | `/negociacion-tactica/` or `/gty/` |

Hub rule: **Abrir** → coach HTML file · **Copiar** → participant folder URL.
