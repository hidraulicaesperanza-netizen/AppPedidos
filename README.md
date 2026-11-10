# Buscador de sellos · Oleohidráulica Esperanza

App web (PWA) para buscar O-rings, respaldos, polipack y limpiavástagos por medidas,
obtener el código del sistema y armar una lista de pedido (copiar o PDF).
Funciona sin internet una vez instalada.

## Subir a GitHub y publicar (GitHub Pages)
1. Creá un repositorio nuevo en GitHub (por ejemplo `buscador-sellos`).
2. Subí **todo el contenido de esta carpeta** a la raíz del repositorio
   (`index.html`, `data.js`, `sw.js`, `manifest.webmanifest`, `logo.png`, `icons/`, `.nojekyll`).
3. En el repositorio: **Settings → Pages → Build and deployment → Source: Deploy from a branch**,
   rama `main`, carpeta `/ (root)` → Save.
4. En un minuto la app queda en `https://TU-USUARIO.github.io/buscador-sellos/`.

## Instalar en el celular
- **Android (Chrome):** abrí el link → menú ⋮ → *Instalar app* / *Agregar a pantalla principal*.
- **iPhone (Safari):** abrí el link → botón Compartir → *Agregar a pantalla de inicio*.

Abrila una vez con internet para que quede guardada; después funciona sin conexión.
(El generador de PDF se descarga de cdnjs la primera vez y también queda en caché.)

## Convertir en APK / app de tienda (opcional)
- Entrá a https://www.pwabuilder.com, pegá la URL de GitHub Pages y descargá el paquete Android.
- O usá Capacitor (`npm i @capacitor/core @capacitor/cli`, `npx cap init`, apuntando `webDir` a esta carpeta).

## Actualizar los datos
Los códigos y medidas están en `data.js` (una fila por artículo:
`[tipo, código, nombre, D.int, D.ext, sección, altura, nº AS568, material]`).
Al cambiar archivos, subí una nueva versión y cambiá `V='sellos-v1'` en `sw.js` (por ejemplo a `sellos-v2`)
para que los celulares tomen la actualización.

## Fuentes de las medidas
- O-ring y respaldo: tabla del PDF (AS568) cruzada por número de medida (2-xxx).
- Polipack: calculadas desde el código en pulgadas; métricos desde el código/nombre.
- Limpiavástago: tomadas del nombre en el Excel.
