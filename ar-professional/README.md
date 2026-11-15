# Redirección ar-professional.vercel.app

Redirige todas las rutas de `ar-professional.vercel.app` a
<https://www.sur-digital.com/ar-professional> con un 308 permanente.

## Desplegar en Vercel

1. <https://vercel.com/new> e importa `github.com/sdad47573-del/vercel-proxies`.
2. **Project Name**: `ar-professional` (así recibe ese subdominio).
3. **Root Directory**: `ar-professional`.
4. Framework **Other**; no toques build ni output, ya vienen en `vercel.json`.
5. Deploy.

## Comprobar

```bash
curl -sSI https://ar-professional.vercel.app/ | grep -iE "^(HTTP|location)"
# esperado: 308 + Location: https://www.sur-digital.com/ar-professional
```
