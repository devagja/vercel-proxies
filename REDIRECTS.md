# Redirecciones de dominios antiguos → sur-digital.com

Cada dominio vive en su propia carpeta porque un subdominio `*.vercel.app`
pertenece al proyecto que lleva ese nombre, y cada sitio de Netlify es
independiente. El repo `sdad47573-del/vercel-proxies` es la fuente de todos.

## Reglas por plataforma

- **Vercel** (`<carpeta>/vercel.json`): `/(.*)` → destino, `permanent: true`
  (308), `framework: null`, `installCommand`/`buildCommand` en `true` y
  `outputDirectory: "public"`. Proyecto nuevo con **Project Name** = dominio sin
  `.vercel.app` y **Root Directory** = su carpeta.
- **Netlify** (`<carpeta>/public/_redirects`): `/*  destino  301!`. En el sitio
  correspondiente, **Publish directory** = `<carpeta>/public`, sin build.

## Mapa

| Dominio antiguo | Destino | Plataforma | Carpeta / proyecto |
|---|---|---|---|
| sergiocruzchacon.vercel.app | /scruz-abogados/ | Vercel | raíz del repo |
| a-style-beauty-salon.vercel.app | /a-style-beauty-salon/ | Vercel | `a-style-beauty-salon/` |
| ar-professional.vercel.app | /ar-professional | Vercel | `ar-professional/` |
| a-fuego-braseria.vercel.app | /a-fuego-braseria | Vercel | `a-fuego-braseria/` |
| a-jalar.vercel.app | /a-jalar | Vercel | `a-jalar/` |
| agustin-el-picoteo.vercel.app | /agustin-el-picoteo | Vercel | `agustin-el-picoteo/` |
| am-industria-del-estilo.netlify.app | /am-industria-del-estilo | Netlify | `am-industria-del-estilo/` |
| barberia-hair-cool.netlify.app | /barberia-hair-cool | Netlify | `barberia-hair-cool/` |
| 1111-coffee-and-bakery.netlify.app | /1111-coffee-and-bakery | Netlify | `1111-coffee-and-bakery/` |
| 78-street-burguer.netlify.app | /78-street-burger/ | Netlify | `78-street-burguer/` |
| a-gusto-el-macizo.netlify.app | /a-gusto-el-macizo | Netlify | `a-gusto-el-macizo/` |
| a-retoral-tapas-y-brasas.netlify.app | /a-retoral-tapas-y-brasas | Netlify | `a-retoral-tapas-y-brasas/` |
| a-roda-restaurante.netlify.app | /a-roda-restaurante | Netlify | `a-roda-restaurante/` |
| abaceria-tinta-de-toro.netlify.app | /abaceria-tinta-de-toro | Netlify | `abaceria-tinta-de-toro/` |
| actitud-centro-belleza.netlify.app | /actitud-centro-belleza | Netlify | `actitud-centro-belleza/` |
| adrizale.netlify.app | /adrizale | Netlify | `adrizale/` |
| aguatapa-cadiz.netlify.app | /aguatapa-cadiz | Netlify | `aguatapa-cadiz/` |
| amorato-malaga.netlify.app | /amorato-malaga | Netlify | `amorato-malaga/` |
| asador-de-camilo.netlify.app | /asador-de-camilo | Netlify | `asador-de-camilo/` |
| asador-la-granja.vercel.app | /asador-la-granja | Vercel | `asador-la-granja/` |
| autana-restaurant.netlify.app | /autana-restaurant | Netlify | `autana-restaurant/` |
| bacchus-terrace.vercel.app | /bacchus-terrace | Vercel | `bacchus-terrace/` |
| bar-los-granainos-miguel.vercel.app | /bar-los-granainos-miguel | Vercel | `bar-los-granainos-miguel/` |

## Comprobar

```bash
# Vercel: 308 + Location al destino
curl -sSI https://a-jalar.vercel.app/ | grep -iE "^(HTTP|location)"
# Netlify: 301 + Location al destino
curl -sSI https://adrizale.netlify.app/ | grep -iE "^(HTTP|location)"
```
