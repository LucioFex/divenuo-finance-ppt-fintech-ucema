# diVenuo Finance — Contexto del proyecto (handoff)

> Documento de continuidad para retomar el trabajo en otra sesión. Última actualización: 2026-06-28.

## 1. Qué es este proyecto

Trabajo Final de la materia **Fintech (UCEMA)**. El grupo debe armar y defender oralmente un **pitch deck de una fintech con IA** como valor central. Decidimos usar como ancla referencial a **diVenuo** (producto real) y presentarlo "como si" fuera una fintech, bajo el nombre académico **diVenuo Finance**.

**Entregable construido:** `index.html` en esta carpeta — un pitch deck HTML autocontenido, navegable por teclado, con estética fintech premium fiel a la marca real de diVenuo.

### Reglas duras
- **Es 100% académico.** El profesor sabe que diVenuo NO es una fintech; el ejercicio es reconstruirlo como tal partiendo de su contexto histórico real (un "sistema de turnos") y sumar valor agregado.
- **El proyecto real de diVenuo vive en `/home/lucio/guzman-estudio` → SOLO LECTURA, JAMÁS modificar.** El RAG curado está en `guzman-estudio/guzman_studio_claude_rag_karpathy/` (índice en `00_index.md`).
- Toda la operación de este TP ocurre en `/home/lucio/TP-Grupal-Fintech-tematica-diVenuo/`.

## 2. La consigna (resumen del PDF)

`Contexto-clases-TrabajoFintech/Consigna – Trabajo Final_ Proyecto Fintech con AI.pdf`:
- Pitch deck de una fintech que **integre IA como parte central** de la propuesta de valor.
- Apartados mínimos: 1) Introducción · 2) Problema · 3) Solución innovadora · 4) Mercado objetivo · 5) Tamaño de mercado (TAM/SAM/SOM) · 6) Modelo de negocio.
- Se sugiere el **framework de Sequoia** (template en `Contexto-clases-TrabajoFintech/Pitch_Deck_Template_Sequoia_Capital_*.pdf`).
- Debe resaltar cómo aborda los temas del curso (Medios de Pago, Open/Embedded Finance, Transformación digital de la banca, etc.).
- **≤ 10 minutos** de exposición · **máximo 6 integrantes** · **todos participan** · nota individual + grupal.

## 3. Qué es diVenuo en la realidad (base del reframe)

SaaS **multi-tenant de turnos** para barberías, peluquerías, estética, peluquería canina y tatuadores (Argentina). Ya hoy:
- Cobra **señas vía Mercado Pago** — cada local (tenant) conecta SU cuenta MP; diVenuo es la **capa de cobros** (mueve dinero real, con split plataforma/local).
- Tiene **billing de suscripciones** in-app (planes Esencial/Profesional/Negocio; MRR real).
- Tiene un **motor de analítica/IA**: predicción de churn dinámico, no-show, señas dinámicas (por reincidencia/primer turno), insights del negocio, forecasting de demanda.
- Multi-sucursal, ~8-9 tenants en producción (Guzman Estudio, Séptimo, Negro Urban Barber, etc.).
- **Marca de plataforma real:** charcoal + dorado + **Work Sans** (la landing v2 es oscura con glow dorado y la "di**V**enuo" con la V en oro). El deck es fiel a esto.

## 4. La tesis del deck (decisiones tomadas con el usuario)

**Tesis:** *diVenuo Finance es la infraestructura financiera de la economía de turnos: cobros, capital y un copiloto de IA para las PyMEs de servicios que la banca ignora.*

**Reframe / ancla histórica:** diVenuo nació como sistema de turnos → gestionar turnos lo llevó a mover dinero (señas con MP) → acumuló el flujo de caja real y en vivo de miles de PyMEs (dato que ningún banco tiene) → diVenuo Finance convierte pagos + datos en infraestructura financiera completa.

Decisiones del usuario (todas las opciones recomendadas):
- **Tesis fintech:** OS financiero vertical (embedded finance) — 3 capas: Pagos embebidos (ya en prod) · Capital/lending · Cerebro de IA.
- **Rol de la IA (central):** underwriting con datos alternativos + copiloto financiero conversacional. El dato propietario (turnos/pagos/cadencia/churn/no-show) → predice cash-flow, score de crédito sin banco, señas dinámicas, copiloto.
- **Mercado:** Argentina → LatAm (aprovecha Mercado Pago y el ejemplo de Pomelo.la).
- **Formato:** slides navegables por teclado (no scroll-landing).
- **Estética:** fintech premium oscura (charcoal + dorado + verde diVenuo) — fiel a la marca real. Fuente **Work Sans**.
- **Números:** concretos pero etiquetados como ilustrativos/proyección.
- **Equipo:** 6 roles C-level con placeholders `ALUMNO1…ALUMNO6`.

### Cifras ilustrativas usadas en el deck
- **Mercado:** TAM US$ 12B · SAM US$ 2,9B (AR+MX+CO+CL, ~2,6M locales × ARPU ~US$1.100/año) · SOM US$ 120M a 5 años (~90k locales, ~1% TAM).
- **Tracción (hoy, basada en lo real):** 9 locales en producción · +15.000 turnos · 0 churn de locales · cobros MP en vivo.
- **Proyección locales:** Hoy 9 → Año1 350 → Año2 2.500 → Año3 9.000 → Año5 28.000.
- **Unit economics:** ARPU maduro ~US$1.100/local/año · CAC US$80 · LTV/CAC >4x · payback <8m.
- **Modelo:** SaaS (ARS 20k–60k/mes) + take-rate de pagos (~1% GMV) + spread de lending + BNPL.
- **ARR proyectado (US$M):** 0,4 → 2,1 → 7,5 → 20 → 45.
- **Ronda:** pre-seed US$1,8M (40% lending/compliance · 30% expansión MX+CO · 20% IA/datos · 10% licencias/ops).

## 5. Estructura del deck (17 slides, Sequoia + consigna)

> **2026-06-26 — Iteración de calidad visual + contenido:**
> - **Slide nueva #10 "El playbook ya creó gigantes" (comparables):** Toast / Shopify / Square / Mindbody / Mercado Pago / Nubank → prueba que el patrón "SaaS vertical → pagos embebidos → crédito con dato propio" ya valió cientos de miles de millones. Remate de posicionamiento: "el Toast de la economía de turnos / el Shopify Capital de las PyMEs de servicios". La pitchea el CMO (Nicolás Grosso). CSS `.logos/.logo-card/.flowline/.punch`.
> - **Fix bug count-up:** bajo `prefers-reduced-motion` (entorno de Lucio) los números quedaban en "0" (Tracción/Modelo). Ahora `countUp(el, instant)` salta al valor final. CRÍTICO porque se presenta así.
> - Renumeradas slides 11→17, array `roles` a 17 entradas, foots y contador OK. Verificado por screenshots (Chrome headless).
>
> Tabla original (16) abajo — desde la #10 corre +1.


| # | Slide | Sequoia | Rol que pitchea |
|---|-------|---------|-----------------|
| 1 | Portada | — | CEO · ALUMNO1 |
| 2 | Equipo (movida al frente, estilo Pomelo) | Team | Equipo · Todos |
| 3 | Company Purpose | Company Purpose | CEO · ALUMNO1 |
| 4 | De turnos a fintech (origen/ancla) | Why Now | CMO · ALUMNO6 |
| 5 | Problema | Problem | CPO · ALUMNO3 |
| 6 | Solución (3 capas) | Solution | CTO · ALUMNO2 |
| 7 | Producto (mockups + copiloto) | Product | CPO · ALUMNO3 |
| 8 | Cerebro de IA (slide estrella) | Solution/Product | Head of AI · ALUMNO4 |
| 9 | Why Now (4 olas, ata temas del curso) | Why Now | Head of AI · ALUMNO4 |
| 10 | Mercado TAM/SAM/SOM | Market Size | CFO · ALUMNO5 |
| 11 | Competencia (mapa 2×2) | Competition | CMO · ALUMNO6 |
| 12 | Modelo de negocio | Business Model | CFO · ALUMNO5 |
| 13 | Tracción | Traction | CMO · ALUMNO6 |
| 14 | Roadmap | Product | CTO · ALUMNO2 |
| 15 | Financials & The Ask | Financials | CFO · ALUMNO5 |
| 16 | Visión / cierre | — | CEO · ALUMNO1 |

**Roles del equipo:** CEO (visión/fundraising) · CTO (arquitectura/pagos/infra) · CPO (producto/UX) · Head of AI·CDO (modelos de riesgo/forecasting/copiloto) · CFO·Head of Risk (modelo financiero/underwriting/unit economics) · CMO·Head of Growth (GTM/expansión).

## 6. Detalles técnicos del `index.html`

- **Un solo archivo autocontenido**, sin build. Solo dependencia externa: Work Sans (Google Fonts) + imágenes de Unsplash.
- **Navegación:** `←`/`→`/espacio/click (desktop)/swipe (mobile); `Home`/`End`; `F` pantalla completa. Barra de progreso, contador, deep-link por hash (ej. `index.html#8` abre la slide de IA).
- **Paleta (CSS vars):** `--ink #120f17` · `--gold #d9b44a` · `--gold-soft #fff8ba` · `--green-2 #27b368` · `--cream #f2f4fc` · texto `#F1EEF6`.
- **Animaciones (todas degradan con `prefers-reduced-motion`):** fondo mesh animado + grano, texto con brillo dorado (`.shine`), count-ups (`.count` con `data-to/data-prefix/data-sep`), barras que crecen (`--h`), cards con sheen + hover-lift, Ken Burns en fotos de fondo, núcleo de IA con pulso.
- **Imágenes Unsplash (free-use, verificadas HTTP 200)** vía `background-image` (si no hay red, cae elegante al degradado):
  - Barbería moody `photo-1585747860715-2ba37e788b70` (portada/problema/cierre)
  - Equipo `photo-1522071820081-009f0129c71c` (slide 2)
  - Circuit/chip `photo-1518770660439-4636190af475` (IA)
  - Obelisco BA `photo-1589909202802-8f4aadce1849` (mercado)
  - Dashboard datos `photo-1551288049-bebda4e38f71` (tracción)
- **Etiqueta de rol:** generada por JS desde el array `roles` (en el `<script>`). Vertical en el borde derecho. Se oculta < 980px.

## 7. Pendientes / próximos pasos

- [x] **Reemplazar `ALUMNO1…ALUMNO6` por nombres reales** (HECHO 2026-06-26): Luciano Esteban (CEO) · Francisco Guarrera (CTO) · Nicolás Morteo (CPO) · Lucas Pittner (Head of AI·CDO) · Ulises Gallardo (CFO·Head of Risk) · Nicolás Grosso (CMO·Head of Growth). Aplicado en los 3 lugares (chip slide 1, cards slide 2 con iniciales en `.av`, array `roles` del script).
- [x] **Sumar fotos de perfil reales** del equipo (HECHO): 6 fotos 300×300 embebidas como data-URI en la slide 2.
- [x] **Justificar las fuentes de los datos** (HECHO 2026-06-28, commit `db36b7b`): fuente sutil abajo de cada slide del deck + sección "Fuentes y bibliografía" (4 págs) anexada al guión PDF (ahora 21 págs) + `fuentes-bibliografia.html` versionado y regenerable. Detalle en la sección 10.
- [ ] (Opcional) Ensayar el reparto de quién dice cada slide según las etiquetas de rol.
- [ ] (Opcional) Ajustes finos de copy/números si el profe pide algo específico.

## 8. Historial de cambios hechos

1. v1: deck de 16 slides, estructura Sequoia, narrativa OS financiero, placeholders ALUMNO.
2. v2: equipo movido a slide 2 (estilo Pomelo); más "flashy" (mesh animado, brillo, count-ups, barras animadas, Ken Burns); imágenes Unsplash.
3. Fix: la "V" con brillo se recortaba arriba → subido `line-height` del título + `box-decoration-break:clone`.
4. Etiquetas de rol por slide (borde derecho) + secciones más grandes (Propósito rediseñada con 3 cards, Solución/Mercado/timelines agrandados, ancho 1200px).
5. v3 (2026-06-26): nombres reales del equipo en los 3 lugares.
6. v4 (2026-06-26) — review punta a punta de calidad visual + contenido:
   - **Slide nueva #10 "El playbook ya creó gigantes" (comparables):** 6 wordmark-cards (Toast, Shopify, Square, Mindbody, Mercado Pago, Nubank) que prueban el patrón "SaaS vertical → pagos embebidos → crédito con dato propio". `.flowline` arriba (las 3 fases), grid `.logos`/`.logo-card` (con sheen + métrica) y caja `.punch` con el remate de posicionamiento. La pitchea el CMO (Nicolás Grosso). Deck pasó de 16 a **17 slides**.
   - **Fix bug count-up reduced-motion:** `countUp(el, instant)` — bajo `prefers-reduced-motion` (entorno de Lucio + proyectores) saltaba a "0" en Tracción/Modelo; ahora muestra el valor final (9 locales · +15.000 turnos · ~US$ 1.100 ARPU · US$ 80 CAC). CRÍTICO porque se presenta así.
   - **Portada reforzada con ancla de comparable:** línea editorial con acento dorado izquierdo — "Lo que *Toast* hizo por los restaurantes y *Shopify* por el comercio — para la *economía de turnos*." (engancha desde el slide 1 y prepara la #10).
   - Renumeración foots 11→17, array `roles` a 17 entradas, contador `tot` 16→17. Todo verificado renderizando con Chrome headless (`scratchpad/shot.sh`) e iterando sobre screenshots.
7. v5 (2026-06-28) — **justificación de fuentes de los datos** (commit `db36b7b`, pusheado a Pages). Ver sección 10.

## 9. Cómo previsualizar / iterar visualmente
- Abrir en navegador: `xdg-open index.html` (o `index.html#10` para saltar a una slide).
- Screenshots headless para iterar sin abrir el navegador: `scratchpad/shot.sh <slide#> <nombre>` usa `google-chrome-stable --headless=new --force-prefers-reduced-motion` (1600×900). Útil además para validar el estado reduced-motion (el real de Lucio).
- **Regenerar la bibliografía del guión:** editar `fuentes-bibliografia.html` → `google-chrome-stable --headless=new --no-pdf-header-footer --print-to-pdf=fuentes.pdf "file://.../fuentes-bibliografia.html"` → `pdfunite <guión-17pp> fuentes.pdf Guion-...pdf`. (El guión base de 17 págs se regenera de su propio HTML, que NO está versionado; conservar un PDF base.)

## 10. Justificación de fuentes (v5, 2026-06-28)
Todo dato del pitch quedó respaldado. Cifras externas verificadas con WebSearch.
- **Deck (`index.html`):** clase CSS `.src` (abajo-derecha, sutil, en cursiva, no pisa la etiqueta de rol vertical; degrada en <980px). Una línea de fuente bajo cada slide con datos (4-6, 8-16), categorizando: *dato propio* / *fuente pública* / *estimación propia*. Se ajustaron 2 cifras de comparables a valores públicos actuales: Toast `~US$13.000M`→`~US$15.000M (jun 2026)`; Square `Millones de PyMEs`→`+US$32.000M prestados desde 2014`.
- **Guión PDF:** +4 págs "Fuentes y bibliografía" anexadas con `pdfunite` (17→**21 págs**). Contenido: portada de sección oscura (estilo cover) + nota metodológica (3 tipos de dato) + mapa fuente-por-slide + **14 referencias** con enlaces: A) comparables [1-6] · B) mercado/brecha MIPYME [7-10: IFC ~87%, BID US$210-250B, INEGI ~190k MX, INET +40k AR] · C) medios de pago/embedded finance [11-13: BCRA Transferencias 3.0, embedded finance LatAm, Pomelo] · D) datos propios diVenuo [14].
- **Fuente regenerable versionada:** `fuentes-bibliografia.html` (A4, Work Sans + Zilla Slab en headings). Corrige el problema histórico de que el `guion.html` original se perdió (solo vivía en scratchpad).
- **Criterio:** TAM/SAM/SOM y proyecciones siguen etiquetados como *estimación propia ilustrativa* (lo honesto académicamente); las fuentes públicas anclan orden de magnitud y contexto, no "demuestran" lo proyectado.

---
*Para retomar: abrir `index.html` en el navegador (o `xdg-open index.html`). Memoria de Claude relacionada: `project-divenuo-finance-tp`.*
