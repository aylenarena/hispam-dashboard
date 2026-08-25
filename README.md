# HISPAM Paid Media Dashboard

Dashboard de performance para Meta Ads y LinkedIn Ads — HISPAM.

## Setup (una sola vez, ~10 minutos)

### 1. Crear el repo en GitHub

1. Entrá a [github.com/new](https://github.com/new)
2. Repository name: `hispam-dashboard`
3. Visibility: **Public** (necesario para que el equipo lea los datos sin autenticarse)
4. ✅ Add a README file
5. → **Create repository**

### 2. Subir los archivos

Subí estos dos archivos al repo:
- `index.html`
- `data/dashboard-data.json`

Podés hacerlo desde la interfaz web de GitHub (botón "Add file → Upload files").

### 3. Crear un Personal Access Token

1. GitHub → Settings → Developer settings → Personal access tokens → **Tokens (classic)**
2. → **Generate new token (classic)**
3. Note: `hispam-dashboard`
4. Expiration: `No expiration` (o 1 año)
5. Scopes: ✅ **repo** (marcá solo este)
6. → **Generate token**
7. **Copiá el token** — lo necesitás en el paso siguiente y no lo vas a poder ver de nuevo

### 4. Completar el config en index.html

Abrí `index.html` y buscá este bloque cerca del inicio del `<script>`:

```js
const CFG = {
  owner: '',    // tu usuario de GitHub, ej: 'aylen-arena'
  repo:  '',    // nombre del repo, ej: 'hispam-dashboard'
  token: '',    // Personal Access Token con permisos repo
  file:  'data/dashboard-data.json'
};
```

Completalo con tus datos:

```js
const CFG = {
  owner: 'aylen-arena',
  repo:  'hispam-dashboard',
  token: 'ghp_xxxxxxxxxxxxxxxxxxxx',
  file:  'data/dashboard-data.json'
};
```

Guardá el archivo y subilo al repo reemplazando el anterior.

### 5. Publicar en Vercel

1. Entrá a [vercel.com](https://vercel.com) → **New Project**
2. Importá el repo `hispam-dashboard` de GitHub
3. → **Deploy** (sin cambiar ninguna configuración)
4. Vercel te da una URL tipo `hispam-dashboard.vercel.app`

✅ **Listo.** Compartí esa URL con tu equipo.

---

## Uso semanal

1. Abrí la URL del dashboard
2. Hacé click en **"Cargar datos"** (botón azul arriba a la derecha)
3. Arrastrá o seleccioná:
   - El `.xlsx` de **Conjuntos de anuncios** de Meta Ads Manager
   - El `.csv` de **Campaign performance report** de LinkedIn Campaign Manager
4. → **Guardar y publicar**

Los datos quedan guardados en el repo y **todo el equipo ve los datos nuevos al instante**, en cualquier browser.

---

## Notas

- Podés subir **varias semanas a la vez** — el dashboard agrega todos los datos
- El token queda en el código del `index.html`. Si el repo es público, cualquiera puede verlo. Si esto es un problema, contactá a tu admin para usar Vercel Environment Variables como capa adicional
- Si actualizás el `index.html` (nuevo feature, cambio visual), subilo al repo y Vercel lo publica en segundos automáticamente
