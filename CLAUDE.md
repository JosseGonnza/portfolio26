# CLAUDE.md — Portfolio Personal PortfolioWeb2026

> Portfolio de Jose González como desarrollador backend.
> Repo independiente de jotagestudio.es. Deploy en dev.jotagestudio.es.
> Última revisión: 2026-05-28

---

## El proyecto

Portfolio personal para empleadores y empresas tech.
Objetivo principal: conseguir prácticas en empresa en **marzo 2027**.

No es una web de servicios — es una presentación profesional técnica.
Audiencia: recruiters, CTOs, responsables de prácticas.

## Posicionamiento

**Backend developer con criterio de producto.**
Stack principal: Java · Spring Boot · SQL · Docker.
Stack complementario demostrado: Astro · Tailwind · Cloudflare (→ JotaGe Studio).

JotaGe Studio se presenta como prueba de entrega en producción, no como pieza central del stack.

## Stack del portfolio (el sitio web en sí)

- Astro 6 + Tailwind CSS 4 (via `@tailwindcss/vite`)
- Cloudflare Pages (deploy)
- Mismo sistema de diseño que jotagestudio.es (dark, #FF5733, Syncopate + Inter)
- Sin framework JS adicional salvo necesidad justificada

## Design tokens — no inventar valores nuevos

| Token          | Valor     |
|----------------|-----------|
| Fondo oscuro   | `#1A1A1A` |
| Superficie     | `#242424` |
| Borde          | `#2E2E2E` |
| Acento naranja | `#FF5733` |
| Texto principal| `#F3F4F6` |
| Texto secundario| `#6B7280` |

Fuentes: Syncopate (titulares), Inter (cuerpo).

## Estructura prevista

```
src/
  components/          ← componentes del portfolio
  layouts/Layout.astro ← layout base con SEO
  pages/
    index.astro        ← página principal (todo en una)
    proyectos/
      api-cartas.astro ← caso de estudio Proyecto 1
public/
  cv-jose-gonzalez.pdf ← CV con estética JotaGe Studio (pendiente)
_docs/
  brief.md             ← estrategia y contenido
  roadmap.md           ← fases y progreso
  proyecto-api-cartas.md ← spec técnica del Proyecto 1
```

## Archivos de referencia

Actualizar cuando corresponda:
- `CLAUDE.md` — si cambia stack, deploy o convenciones
- `_docs/brief.md` — si cambia posicionamiento o secciones
- `_docs/roadmap.md` — marcar fases completadas
- `_docs/proyecto-api-cartas.md` — si cambia el spec del Proyecto 1

## Convenciones

- Componentes: PascalCase (`HeroPortfolio.astro`, `ProyectoCard.astro`)
- Clases Tailwind: inline siempre, sin `@apply`
- Estilos: `<style>` en cada componente
- Sin WhatsAppFloat — este portfolio no es para captar clientes de hostelería

## Proyectos del portfolio (los que se van a construir y mostrar)

| # | Proyecto | Stack | Estado |
|---|----------|-------|--------|
| 1 | API REST cartas digitales | Spring Boot + PostgreSQL + JWT + Railway | Por construir |
| 2 | API costes de recetas | Spring Boot + SQL + Docker | Pendiente |
| 3 | Workout log API | Spring Boot + SQL + Docker | Pendiente |

Ver spec detallada de cada uno en `_docs/`.

## Pendientes conocidos

- [ ] Inicializar proyecto Astro en esta carpeta
- [ ] Crear repo en GitHub (`portfolio2026` o similar)
- [ ] Conectar Cloudflare Pages → deploy automático
- [ ] Configurar subdominio `dev.jotagestudio.es` en DonDominio + Cloudflare
- [ ] Construir Proyecto 1 (API cartas) en repo separado
- [ ] CV PDF con estética JotaGe Studio
