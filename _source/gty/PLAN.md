# GTY — Plan de empaquetado (híbrido TCM + CargoSprint)

**Módulo:** Negociación Táctica y Empresarial (*Getting to Yes*)  
**Cliente:** Tramontina México · Grupo B  
**Duración:** 1 sesión · 3 horas  
**Estado:** Fuentes en `_source/gty/` · HTML en `gty/` · Forms/QR cableados (listo para push Vercel)  

**Decisión de producto:** **híbrido** (proyección tipo CargoSprint + landings/guía/role-play tipo TCM)

---

## 1. Objetivo del plan

Dejar el taller GTY listo de sala con:

1. **Deck fullscreen** para proyectar (timers, pilares, reglas de simulación, debrief, QR).
2. **Landing de participante** alineada al portal Tramontina (`tcm/`, `hwf/`).
3. **Guía del facilitador** minuto a minuto (segunda pantalla / coach).
4. **Role-play empaquetado** (mapa GTY + fichas de rol), compartido solo cuando toca.
5. **Tres Forms + QR** (termómetro, registro de simulación, carta compromiso).

No se adopta el handbook monolítico de CargoSprint: el “handbook liviano” es `index.html` + `role-play.html`.

---

## 2. Por qué híbrido

| Necesidad GTY | Patrón que lo cubre |
| --- | --- |
| Proyectar teoría, timers y fases con notes (tecla **S**) | CargoSprint `deck/session-01.html` |
| Misma UX que el resto del portal Tramontina | TCM `index.html` + `facilitador.html` |
| Role-play sin spoilers desde el landing | TCM `role-play.html` (link solo del coach) |
| Forms / QR / carta compromiso | TCM + specs en `apoyo-visual` |

---

## 3. Estructura de entregables

```
gty/                          # publicado en Vercel (NO va en _source)
├── index.html                # Landing participante
├── facilitador.html          # Guía coach (noindex)
├── role-play.html            # Mapa + roles A/B1/B2 (no enlazado desde landing)
├── deck/
│   ├── index.html            # Hub del deck
│   └── session-01.html       # Presentación 3h (flechas · S notes · F fullscreen)
└── qr/                       # PNGs de Forms 1–3

_source/gty/                  # diseño / excluded via .vercelignore
├── PLAN.md                   # este documento
├── brief
├── agenda
├── apoyo-visual
├── guia-intstructor
├── angulos-objecion
└── simulacion
```

### URLs de share (añadir a `_source/SHARE-URLS.md` al publicar)

| Audiencia | URL |
| --- | --- |
| Participantes | `/gty/` |
| Role-play (pegar en chat al minuto ~01:15) | `/gty/role-play.html` |
| Coach — guía | `/gty/facilitador.html` |
| Coach — deck | `/gty/deck/` → `session-01.html` |

Regla TCM: landings de participante **sin** navegación cruzada a otros talleres ni al role-play.

---

## 4. Quién usa qué en sala

| Tiempo | Bloque | Proyecta (deck) | Participante | Coach (2ª pantalla) |
| --- | --- | --- | --- | --- |
| 00:00–00:10 | Margen + termómetro | M1: título, timer 10′, QR Form 1 | Form 1 / `/gty/` | `facilitador.html` apertura |
| 00:10–00:20 | Encuadre | Resumen Form 1 + agenda | Landing | Guion encuadre |
| 00:20–01:05 | 4 pilares GTY | M2: matriz Tradicional vs Principios + dilema | Cheatsheet en landing (opcional) | Guion pilares + `angulos-objecion` |
| 01:05–01:15 | Break | Timer 10′ | — | — |
| 01:15–01:30 | Prep mapa | M3: fase 1 + instrucciones | **`/gty/role-play.html`** (mapa) | Circular; sin interrumpir |
| 01:30–01:55 | Role-play | M3: fases 5′ / 15′ / 5′ | Role-play (roles) | Sombra táctica; inyección min 12 |
| 01:55–02:15 | Feedback + registro | M3: QR Form 2 | Form 2 | Detener a tiempo |
| 02:15–02:40 | Debrief | M4: métricas / preguntas plenaria | — | Preguntas de desbloqueo |
| 02:40–03:00 | Compromiso | QR Form 3 + cierre | Form 3 / bloque landing | Guion de cierre |

---

## 5. Mapeo fuente → entregable

| Fuente (`_source/gty/`) | Alimenta |
| --- | --- |
| `brief` | Alcance, audiencia, entregables esperados, tono |
| `agenda` | Timing del deck + secciones de `facilitador.html` |
| `apoyo-visual` | Copy de slides M1–M4; specs de Forms 1–3; mensajes en pantalla |
| `guia-intstructor` | Cuerpo de `facilitador.html`; checklist pre-sesión; guiones |
| `angulos-objecion` | Bloque “objeciones” en facilitador + `data-notes` del deck |
| `simulacion` | `role-play.html` (fichas) + slides M3 + notas de sombra del coach |

### Separación de spoilers (crítica)

| Contenido | Dónde sí | Dónde no |
| --- | --- | --- |
| Intereses ocultos B1/B2 | Ficha del rol B en `role-play.html` (sección colapsada o pestaña por rol) | Landing, deck proyectado a todos, Form 1 |
| BATNA / límites del Comercial | Ficha Rol A + mapa | Ficha B (solo postura e intereses propios) |
| Respuestas a objeciones GTY | `facilitador.html` + notes **S** | Landing / role-play participante |
| Claves de “cuándo ceder” (B) | Solo ficha B | Rol A |

---

## 6. Spec de cada entregable

### 6.1 `deck/session-01.html` (patrón CargoSprint)

- HTML autocontenido; navegación: →/Espacio, ←, **S** notes, **F** fullscreen, Home/End.
- Visual: presentación limpia (puede diferir del look “documento” de TCM); branding Tramontina/{E} en hero y pie.
- Secciones mínimas de slides:
  1. Hero — título *Negociación Táctica y Empresarial: De la Posición al Interés*
  2. M1 — termómetro + QR Form 1 + timer
  3. Encuadre — lectura de Form 1 + agenda 3 h
  4. M2 — 4 pilares (Tradicional ↔ Principios), uno o más slides por pilar
  5. Dilema de caso breve (pregunta inductiva)
  6. Break + timer
  7. M3 — reglas de la mesa + diagrama Prep → Simulación → Feedback
  8. Timers de fase role-play
  9. QR Form 2
  10. M4 — debrief (placeholders de métricas si Forms aún no alimentan dashboard vivo)
  11. Preguntas de plenaria
  12. Cierre + QR Form 3 + mensaje “dueños de su negocio”
- Notes: guion corto + 1–2 ángulos de objeción por pilar cuando aplique.
- Hub `deck/index.html` con link a `session-01.html` (una sola sesión).

**Plan B dashboard:** si no hay integración Forms→gráficos en vivo, el slide M4 muestra las 3 métricas como *preguntas de conteo en sala* (manos alzadas / lectura verbal del coach desde respuestas de Form 2).

### 6.2 `index.html` (patrón TCM — participante)

- Hero + badge programa.
- Objetivo de la sesión (1 párrafo).
- Agenda resumida (5 bloques).
- Referencia de escritorio: 4 pilares + definición BATNA (sin casos spoiler).
- Zona CTA: QR Form 1 + QR Form 3 (compromiso); Form 2 puede vivir solo en deck/role-play.
- **Sin** link a `role-play.html`, `facilitador.html` ni otros talleres.
- Look & feel alineado a `tcm/index.html` / `hwf/index.html`.

### 6.3 `facilitador.html` (patrón TCM — coach)

- `noindex`.
- Sidebar por bloque de agenda.
- Checklist técnico (−30 min): deck, timers, 3 QR, segunda pantalla.
- Por bloque: objetivo, acción, guion copy-paste, notas de control.
- Matriz de objeciones (`guia-intstructor` §3 + `angulos-objecion`).
- Enlaces coach-only: deck, role-play, Forms (cuando existan URLs).
- Instrucciones de sombra táctica e inyección de presión (desde `simulacion` §4).

### 6.4 `role-play.html` (patrón TCM — ejercicio)

- Intro: objetivo del módulo + tiempos (15′ / 25′ / 20′).
- **Mapa de preparación GTY** (hoja de trabajo): intereses, variables ×3, BATNA/límite.
- Selector o secciones claras por rol:
  - **Rol A** — Líder Comercial
  - **Rol B1** — Cliente estratégico
  - **Rol B2** — Finanzas / Operaciones
- Micro-estructura del role-play (0–5 / 5–20 / 20–25) visible para ambos.
- QR / link Form 2 al final.
- No enlazado desde `index.html`; el coach pega la URL en el chat/pantalla al iniciar Módulo 3.

### 6.5 Forms + `qr/`

| Form | Nombre tentativo | Momento | Campos (fuente: `apoyo-visual`) |
| --- | --- | --- | --- |
| 1 | Termómetro de la Industria | 00:00–00:10 | Poder 1–5; factor de fricción; fortaleza 1–2 palabras |
| 2 | Registro del Caso Práctico | ~02:05 | Acuerdo sí/no; nivel de descuento; monedas de cambio |
| 3 | Carta Compromiso GTY | 02:40–03:00 | Compromiso externo (cierres); compromiso autonomía interna |

URLs y QR live en `_source/gty/forms` + `gty/qr/`. HTML cableado (landing, facilitador, role-play, deck).

---

## 7. Criterios de “listo de sala”

- [x] Fuentes `_source/gty/*` **guardadas en disco** (incl. `apoyo-visual` persistido 2026-09-05)
- [x] Forms 1–3 creados + URLs + PNG en `gty/qr/` (`form-1-termometro`, `form-2-registro`, `form-3-compromiso`)
- [x] `deck/session-01.html` navegable end-to-end con notes
- [x] `facilitador.html` cubre 180′ + objeciones + checklist
- [x] `role-play.html` con mapa + 3 fichas sin filtrar intereses cruzados
- [x] `index.html` sin link a role-play
- [x] Entrada GTY en hub `index.html` del repo + filas en `_source/SHARE-URLS.md`
- [ ] Dry-run 3 h (timers, QR, asignación de 13 parejas Escenario A/B)

---

## 8. Orden de construcción

1. **Persistir fuentes** — guardar/escribir `_source/gty/{brief,agenda,apoyo-visual,guia-intstructor,angulos-objecion,simulacion}`.
2. **Forms** — crear 1–3; pegar URLs en un stub `forms` o tabla en este PLAN; generar QR.
3. **Deck** — `gty/deck/session-01.html` + hub (desbloquea proyección).
4. **Facilitador** — `gty/facilitador.html`.
5. **Role-play** — `gty/role-play.html` (mapa + roles).
6. **Landing** — `gty/index.html`.
7. **Portal** — link en `/index.html` + `SHARE-URLS.md`.
8. **Dry-run** — ajustar timings y copy según fricción real.

Dependencia suave: el deck puede salir con QR placeholder; no bloquear HTML por Forms, pero **sí** bloquear sesión real sin Forms 1–3.

---

## 9. Fuera de alcance (v1)

- Handbook monolítico tipo `handbook-preview.html` de CargoSprint.
- Dashboard automático Forms→gráficos embebidos (v1 = plan B conteo en sala / lectura coach).
- Session-02 / multi-día.
- PDF print-ready cliente (export posterior si se pide).
- Integración métricas al dashboard plataforma {E} (mencionado en brief; tracking post-sesión aparte).

---

## 10. Referencias de patrón

| Referencia | Uso |
| --- | --- |
| `tcm/index.html`, `tcm/facilitador.html`, `tcm/role-play.html` | UX, spoilers, QR, portal |
| `mini-GL/.../written-etiquette/build/facilitator/deck/session-01.html` | Controles de slides + notes |
| `_source/SHARE-URLS.md` | Política de share instructor vs participante |
| `.vercelignore` | `_source/` no se publica |

---

## 11. Historial de decisiones

| Fecha | Decisión |
| --- | --- |
| 2026-09-05 | Empaquetado **híbrido** TCM + CargoSprint (no solo TCM, no solo handbook CS). |
| 2026-09-05 | Una sola sesión deck (`session-01`); handbook = landing + role-play. |
| 2026-09-05 | Role-play sin link desde landing (regla TCM). |
| 2026-09-05 | Dashboard vivo opcional; v1 con plan B de debrief manual. |
| 2026-09-05 | HTML híbrido shipado (deck 19 slides, facilitador 8 pasos, landing, role-play). Forms 1–3 pendientes. |
| 2026-09-07 | QR renombrados (`form-1|2|3-*.png`), URLs en hub `forms`, HTML cableado — listo para push Vercel. |
