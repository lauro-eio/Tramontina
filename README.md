# Tramontina

Instructor-facing static site (`lauro-eio/Tramontina`).

**Schema:** [`themes/WORKSHOP-SCHEMA.md`](themes/WORKSHOP-SCHEMA.md)  
Also: [`AUTHORING.md`](AUTHORING.md) · [`PROGRAM.md`](PROGRAM.md) · [`_source/SHARE-URLS.md`](_source/SHARE-URLS.md)

## Layout

```text
themes/{code}/              # short code you manage: gty, tcm, hwf
  README.md                 # commercial title + public slug
  index.html                # instructor hub
  group-a|b/…
themes/cierre/{jul|oct|feb}/
```

No root shortcuts. Vercel rewrites long public slugs onto `themes/{code}/`.

## URLs

| Audience | Example |
| --- | --- |
| You (builder) | `/themes/gty/` |
| Participants | `/negociacion-tactica/group-a/leadership-session/` |
| Cierre | `/cierre/jul/` |

Hub: **Abrir** → local facilitador · **Copiar** → public long URL.
