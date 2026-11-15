# Redirección sergiocruzchacon.vercel.app

Proyecto estático que redirige **todas** las rutas de `sergiocruzchacon.vercel.app`
a <https://www.sur-digital.com/scruz-abogados/> con un redirect permanente (308).

- `vercel.json`: regla `/(.*)` → destino, más `X-Robots-Tag: noindex`.
- `index.html`: respaldo con `meta refresh` + JavaScript por si la regla no aplica
  (por ejemplo, al abrir el archivo en local).

## Desplegar en Vercel

1. Ve a <https://vercel.com/new> e importa el repositorio de este proyecto.
2. En **Root Directory** selecciona `redirect` (importante: no la raíz del monorepo).
3. Framework Preset: **Other**. Sin build command ni output directory.
4. Deploy.
5. En **Settings → Domains** del proyecto, añade `sergiocruzchacon.vercel.app`
   si no es ya el dominio del proyecto (el subdominio `*.vercel.app` se asigna
   al proyecto que lo tenga registrado; si otro proyecto lo usa, quítalo primero).

Desde la CLI:

```sh
cd redirect
npx vercel --prod
```

## Comprobar

```sh
curl -sI https://sergiocruzchacon.vercel.app/
# esperado: 308 y location: https://www.sur-digital.com/scruz-abogados/

curl -sI https://sergiocruzchacon.vercel.app/cualquier/ruta
# también redirige al mismo destino
```
