# Redirección a-style-beauty-salon.vercel.app

Proyecto estático que redirige **todas** las rutas de
`a-style-beauty-salon.vercel.app` a
<https://www.sur-digital.com/a-style-beauty-salon/> con un 308 permanente.

Un subdominio `*.vercel.app` pertenece al proyecto que tiene ese nombre, así que
esto va como **proyecto aparte** del de `sergiocruzchacon` (que sirve desde la
raíz del repo).

- `vercel.json`: `/(.*)` → destino, sin instalación ni build y con
  `outputDirectory: "public"` (sin eso Vercel falla con
  `STATIC_BUILD_NO_OUT_DIR`).
- `public/index.html`: respaldo con `meta refresh` + `location.replace()`, por si
  una ruta llegara a servirse como fichero.

## Desplegar en Vercel

1. <https://vercel.com/new> e importa el repositorio
   (`github.com/sdad47573-del/vercel-proxies`).
2. **Project Name**: `a-style-beauty-salon` (así recibe ese subdominio).
3. **Root Directory**: `a-style-beauty-salon`.
4. Framework Preset: **Other**. No toques build ni output: ya vienen en el
   `vercel.json`.
5. Deploy.

## Comprobar

```bash
curl -sSI https://a-style-beauty-salon.vercel.app/ | grep -iE "^(HTTP|location)"
curl -sSIL https://a-style-beauty-salon.vercel.app/cualquier/ruta | grep -iE "^(HTTP|location)"
# esperado: 308 + Location: https://www.sur-digital.com/a-style-beauty-salon/
```
