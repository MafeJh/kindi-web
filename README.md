# Kindi Web

Sitio de Kindi (accesorios intencionados + servicios de sanación energética), construido con Astro.

## Estructura

```
src/
  data/
    productos.json   ← edita aquí para agregar/quitar/cambiar productos
    servicios.json   ← edita aquí para cambiar servicios y precios
  pages/
    index.astro       (Inicio)
    productos.astro   (Productos)
    servicios.astro   (Servicios)
  components/
    Header.astro
    Footer.astro
  layouts/
    Layout.astro
  styles/
    global.css        ← colores, tipografía y estilos de marca
```

## 1. Subir el proyecto a GitHub (github.com/MafeJh/kindi-web)

Desde una terminal, dentro de esta carpeta:

```bash
git init
git add .
git commit -m "Sitio inicial de Kindi"
git branch -M main
git remote add origin https://github.com/MafeJh/kindi-web.git
git push -u origin main
```

Si el repositorio `kindi-web` no existe todavía en tu cuenta, créalo primero en
github.com/new (sin README, sin .gitignore — este proyecto ya los trae) y
luego corre los comandos de arriba.

## 2. Conectar con Netlify (gratis)

1. Entra a [app.netlify.com](https://app.netlify.com) e inicia sesión con tu
   cuenta de GitHub.
2. "Add new site" → "Import an existing project" → elige `kindi-web`.
3. Netlify detecta automáticamente la configuración (ya está en
   `netlify.toml`): build command `npm run build`, carpeta `dist`.
4. Dale "Deploy". En un par de minutos tendrás tu sitio en
   `algo-random.netlify.app`.
5. En "Site settings" → "Change site name" puedes ponerle un nombre propio,
   por ejemplo `kindi.netlify.app` (si está disponible) o
   `soplodekindi.netlify.app`.

Desde ese momento, **cada vez que hagas `git push` a `main`, Netlify vuelve a
publicar el sitio automáticamente.**

## 3. Cómo actualizar productos o servicios

### Opción A — Tú misma, desde github.com (sin instalar nada)
1. Ve a `github.com/MafeJh/kindi-web/blob/main/src/data/productos.json`
   (o `servicios.json`).
2. Click en el ícono de lápiz (editar).
3. Agrega, quita o edita un producto siguiendo el mismo formato:
   ```json
   {"nombre":"Cuarzo Verde Aventurina","categoria":"cadenas","descripcion":"Cadena con cuarzo aventurina para la buena fortuna.","precio":"S/ 99","intencion":"abundancia"}
   ```
   Categorías válidas: `cadenas`, `aretas`, `manillas`, `anillos`.
   Intenciones válidas (o `null` si no aplica): `amor`, `calma`, `abundancia`,
   `proteccion`, `claridad`.
4. Al final de la página, click "Commit changes". Netlify vuelve a publicar
   el sitio solo, en 1-2 minutos.

### Opción B — Pídeme a mí (Claude) que lo actualice
Solo dime qué producto o servicio agregar/cambiar y con qué datos, y yo edito
el JSON y te dejo el archivo listo (o hago el commit si conectamos GitHub
directamente en el chat).

## Comandos locales (opcional, si quieres verlo en tu computador)

```bash
npm install
npm run dev       # servidor local en localhost:4321
npm run build     # genera el sitio final en /dist
```
