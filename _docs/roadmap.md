# Roadmap — Portfolio Personal (dev.jotagestudio.es)

> Dos líneas de trabajo en paralelo: la web del portfolio y los proyectos que muestra.
> Actualizar al completar cada punto.

---

## Línea A — Web del portfolio (PortfolioWeb2026)

### Fase A0 — Setup inicial
- [ ] Inicializar proyecto Astro en `/PortfolioWeb2026/`
- [ ] Crear repo GitHub (`portfolio2026`)
- [ ] Conectar Cloudflare Pages con deploy automático desde main
- [ ] Configurar subdominio `dev.jotagestudio.es` → Cloudflare Pages
- [ ] Layout base con SEO (title, description, og:image por página)

### Fase A1 — Contenido y componentes
- [ ] `HeroPortfolio.astro` — pitch backend + stack + disponibilidad prácticas mar 2027
- [ ] `StackGrid.astro` — producción (Astro/Tailwind/Cloudflare) vs. académico (Java/Spring/SQL/Docker)
- [ ] `ProyectosGrid.astro` — cards de proyectos con enlace a caso de estudio
- [ ] `CasoEstudio.astro` — plantilla para páginas de proyecto individual
- [ ] `FormacionTimeline.astro` — DAW + IBM SkillsBuild + Cocina
- [ ] `ContactoPortfolio.astro` — email directo + formulario con aviso GDPR
- [ ] Footer con links: GitHub · LinkedIn · jotagestudio.es

### Fase A2 — CV PDF
- [ ] Rediseñar CV con estética JotaGe Studio (dark, #FF5733, Syncopate)
- [ ] Exportar PDF → `/public/cv-jose-gonzalez.pdf`
- [ ] Enlazar desde la web

### Fase A3 — Casos de estudio de proyectos
- [ ] Página `proyectos/api-cartas.astro` — caso completo del Proyecto 1
- [ ] Añadir cuando estén los proyectos 2 y 3

### Fase A4 — Distribución
- [ ] Actualizar LinkedIn con `dev.jotagestudio.es`
- [ ] Añadir enlace desde jotagestudio.es (Header + Footer + SobreMi)
- [ ] Retirar referencias a jossegonnza.vercel.app
- [ ] Compartir con primeros contactos

---

## Línea B — Proyectos backend (repos independientes)

### Proyecto 1 — API REST cartas digitales ⭐
Ver spec completa en `_docs/proyecto-api-cartas.md`

- [ ] B1.1 — Modelo de datos + esquema PostgreSQL (Cliente, Sección, Plato)
- [ ] B1.2 — Entidades JPA + relaciones
- [ ] B1.3 — Repositorios + servicios
- [ ] B1.4 — Controladores REST (endpoints CRUD)
- [ ] B1.5 — Autenticación JWT en endpoints de escritura
- [ ] B1.6 — SpringDoc OpenAPI (Swagger UI)
- [ ] B1.7 — Deploy en Railway (API + PostgreSQL)
- [ ] B1.8 — Subdominio `api.jotagestudio.es` → Railway
- [ ] B1.9 — Frontend demo Rincón de Blas (Astro, consume API)
- [ ] B1.10 — Frontend demo Café Extracto (Astro, consume API)
- [ ] B1.11 — README completo con arquitectura y cómo arrancar

### Proyecto 2 — API costes de recetas
- [ ] Pendiente de spec — arrancar cuando Proyecto 1 esté en producción

### Proyecto 3 — Workout log API
- [ ] Pendiente — prioridad baja

---

## Orden recomendado

1. A0 (setup portfolio) → tener la web base antes de tener contenido
2. B1.1–B1.5 (core del Proyecto 1) → lo más importante para prácticas
3. A1 (contenido web) → mientras el Proyecto 1 está en Railway
4. B1.6–B1.11 (Swagger + deploy + demos) → cerrar el Proyecto 1
5. A2 (CV PDF) + A3 (caso de estudio del P1)
6. A4 (distribución) → cuando todo esté presentable

---

## Decisiones tomadas

- 2026-05-28 — Portfolio como repo independiente, desplegado en `dev.jotagestudio.es`
- 2026-05-28 — Posicionamiento: backend Java developer (no frontend, no full-stack genérico)
- 2026-05-28 — Proyecto 1 confirmado: API cartas digitales con Spring Boot + PostgreSQL + Railway
- 2026-05-28 — Proyecto 2 confirmado: API costes de recetas (pendiente de spec)
- 2026-05-28 — Proyecto 3 (workout log): pendiente, prioridad baja
- 2026-05-28 — Dashboard Cloudflare Workers (gestión cartas JotaGe): es herramienta de negocio, no portfolio
- 2026-05-28 — Swagger (SpringDoc OpenAPI) obligatorio en todos los proyectos Spring Boot
