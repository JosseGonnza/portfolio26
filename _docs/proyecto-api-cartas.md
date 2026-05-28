# Spec — Proyecto 1: API REST Cartas Digitales

> Proyecto backend para portfolio. Repo independiente, desplegado en Railway.
> No toca ni reemplaza las cartas estáticas de JotaGe Studio.

---

## Contexto

JotaGe Studio gestiona cartas digitales con arquitectura estática (carta.ts → Astro → Cloudflare).
Este proyecto demuestra la alternativa dinámica: los datos viven en PostgreSQL y la carta
hace fetch a la API en tiempo real. Misma solución, arquitectura opuesta. Eso es lo interesante.

## Stack

| Capa | Tecnología |
|------|------------|
| Backend | Java + Spring Boot |
| Base de datos | PostgreSQL |
| ORM | Spring Data JPA / Hibernate |
| Autenticación | JWT (solo escritura) |
| Documentación | SpringDoc OpenAPI (Swagger UI) |
| Deploy backend | Railway |
| Deploy frontends demo | Cloudflare Pages |
| Frontend demos | Astro (o vanilla JS) |

## Endpoints

```
GET    /clientes                       → lista todos los clientes
GET    /clientes/{slug}/carta          → carta completa (público, sin auth)
POST   /clientes                       → crear cliente (requiere JWT)
PUT    /platos/{id}                    → actualizar plato (requiere JWT)
DELETE /platos/{id}                    → eliminar plato (requiere JWT)
POST   /clientes/{slug}/secciones      → añadir sección (requiere JWT)
PUT    /secciones/{id}                 → actualizar sección (requiere JWT)
DELETE /secciones/{id}                 → eliminar sección (requiere JWT)
```

GET /clientes/{slug}/carta es público — lo llaman los frontends demo.
El resto requiere JWT — se demuestra via Swagger UI en entrevista.

## Modelo de datos

```
Cliente
  id, slug, nombre, descripcion
  → tiene muchas Secciones

Sección
  id, nombre, orden, clienteId
  → tiene muchos Platos

Plato
  id, nombre, descripcion, precio, disponible, alergenos, seccionId
```

## Demos

Dos frontends Astro que consumen la API:

- `rincon-de-blas` — carta tipo P1: nombre + precio + disponibilidad
- `cafe-extracto` — carta tipo P2: nombre + descripción + precio + alérgenos

Datos propios (no son los clientes reales, son las demos que Jose creó para la empresa).
Estos sí van commiteados en el repo público.

## Dominios

- `api.jotagestudio.es` → Railway (subdominio nuevo en DonDominio)
- Demos: subdominios de Cloudflare Pages hasta que haya más proyectos que justifiquen subdominio propio

## Costes estimados

Railway: $0 los primeros 30 días, ~$1-5/mes después según uso.
No requiere tarjeta para empezar. Deploy automático desde push a GitHub.

## Orden de construcción

1. Modelo de datos + esquema PostgreSQL
2. Entidades JPA con relaciones
3. Repositorios + servicios
4. Controladores REST endpoints básicos
5. Autenticación JWT en endpoints de escritura
6. SpringDoc OpenAPI → Swagger UI accesible en `/swagger-ui.html`
7. Deploy en Railway con PostgreSQL
8. Subdominio `api.jotagestudio.es` → Railway
9. Frontend demo Rincón de Blas consumiendo API
10. Frontend demo Café Extracto consumiendo API
11. README con arquitectura, decisiones y cómo arrancarlo local

## Lo que demuestra

- API REST con rutas limpias y separación de responsabilidades
- Modelo relacional real (no un CRUD plano)
- Spring Boot + JPA + PostgreSQL en producción
- JWT en escritura, GET público (decisión de diseño explicable)
- Swagger UI funcional — el reclutador lo puede probar en vivo
- Deploy real en Railway con dominio propio
- Dominio de negocio propio — no un TODO list inventado

## Lo que NO es

- No reemplaza las cartas estáticas de JotaGe Studio
- No tiene panel de administración con UI (se demuestra via Swagger)
- No es SaaS ni plataforma multiusuario pública
- No tiene relación con el dashboard Cloudflare Workers (ese es herramienta interna de negocio)
