# Redirección barberia-hair-cool.netlify.app

Redirige todas las rutas de `barberia-hair-cool.netlify.app` a
<https://www.sur-digital.com/barberia-hair-cool> con un 301 forzado.

Netlify no usa `vercel.json`: la regla vive en `public/_redirects`
(`/*  destino  301!`), que es lo que Netlify lee en el directorio publicado. El
`301!` hace que la regla se aplique incluso si existiera un fichero con esa ruta.

## Desplegar en Netlify

1. Entra en el sitio `barberia-hair-cool` (o crea uno con ese nombre, para
   conservar el subdominio).
2. *Build & deploy* → **Publish directory**: `barberia-hair-cool/public`, sin
   build command.
3. Deploy. O con la CLI, desde esta carpeta:

```bash
netlify link          # elige el sitio barberia-hair-cool
netlify deploy --prod --dir=public
```

## Comprobar

```bash
curl -sSI https://barberia-hair-cool.netlify.app/ | grep -iE "^(HTTP|location)"
# esperado: 301 + Location: https://www.sur-digital.com/barberia-hair-cool
```
