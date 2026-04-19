# Spike de viabilidad: generación de imágenes para posts

## Objetivo
Validar si podemos generar imágenes relevantes por post y publicarlas automáticamente en el blog.

## Hipótesis
Es viable generar hero images con modelo generativo, versionarlas en el repo y enlazarlas vía frontmatter (`heroImage`).

## Prueba ejecutada
- Modelo: `openai/gpt-image-1`
- Formato: PNG
- Resolución: `1536x1024` (landscape)
- Flujo:
  1. Generar imagen por prompt temático.
  2. Guardar en `src/assets/generated/`.
  3. Actualizar frontmatter de cada post con `heroImage`.
  4. Build + deploy en Cloudflare Pages.

## Posts actualizados
- `2026-04-18-opiniones-con-criterio.md`
- `2026-04-19-heat-seeking-missile-for-pain.md`
- `2026-04-19-mindset-carol-dweck.md`

## Resultado
✅ Viable y funcional de extremo a extremo.

## Costo/tiempo estimado (operativo)
- 1 imagen por post: ~30-90s de generación + revisión.
- Integración por post: ~1-2 min (copiar asset + frontmatter).

## Riesgos
- Estilo inconsistente entre posts si no hay guía visual.
- Resultados genéricos si el prompt es débil.
- Posibles artefactos visuales sin revisión humana.

## Recomendación
Estandarizar un mini-brief por post:
- tono visual,
- paleta,
- composición,
- elementos prohibidos,
- proporción fija.

Con eso, se puede automatizar un pipeline “post + hero image” de forma confiable.
