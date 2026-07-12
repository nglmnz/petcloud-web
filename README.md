# PET CLOUD — Sitio web (Quarto + GitHub Pages)

## Despliegue desde RStudio

### 1. Abrir el proyecto
Descomprime esta carpeta y en RStudio: **File → Open Project** (o crea un `.Rproj` con `usethis::create_project(".")` dentro de la carpeta).

### 2. Vista previa local
En la Terminal de RStudio:

```bash
quarto preview
```

### 3. Crear el repo en GitHub
En la Consola de R:

```r
usethis::use_git()
usethis::use_github()   # crea el repo remoto y hace push
```

(Requiere token configurado; si no lo tienes: `usethis::create_github_token()` y luego `gitcreds::gitcreds_set()`.)

### 4. Publicar en GitHub Pages
En la Terminal:

```bash
quarto publish gh-pages
```

Esto crea la rama `gh-pages` y publica automáticamente. El sitio quedará en:
`https://TU-USUARIO.github.io/NOMBRE-DEL-REPO`

### 5. Ajustes pendientes
- Reemplazar `TU-USUARIO` en `_quarto.yml` (site-url, repo-url, ícono GitHub).
- Completar contacto real en `colaboracion.qmd`.
- Cada actualización: commit + push + `quarto publish gh-pages` de nuevo.

## Estructura

```
_quarto.yml       → configuración del sitio y navbar
custom.scss       → tema visual (paleta PET + estados del dashboard)
index.qmd         → portada
proyecto.qmd      → diagnóstico, objetivos, impacto, cronograma
arquitectura.qmd  → documento vivo de arquitectura (con diagrama Mermaid)
colaboracion.qmd  → alianzas buscadas y contacto
```
