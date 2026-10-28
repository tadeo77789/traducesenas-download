# TraduceSeña — descarga para Android

Página de descarga de la app Android de [TraduceSeña](https://traducesenas.tech), publicada con GitHub Pages:

**https://tadeo77789.github.io/traducesenas-download/**

La web (botón "Descargar app para Android" de la landing) enlaza a esta página. El archivo APK **no se guarda en el repo**: va como adjunto de un *Release* de GitHub.

## Publicar una versión nueva del APK

1. Compila el APK con EAS (`eas build -p android --profile preview` en el repo del Frontend) y descárgalo.
2. Renómbralo exactamente **`traducesenas.apk`**. La página y el enlace fijo buscan ese nombre.
3. Crea el Release con la versión de `app.json` (`expo.version`):

   ```bash
   gh release create v1.0.0 traducesenas.apk -R tadeo77789/traducesenas-download \
     --title "TraduceSeña 1.0.0" --notes "Cambios de esta versión."
   ```

   También se puede hacer desde GitHub: *Releases → Draft a new release*, etiqueta `v1.0.0` y adjuntar el archivo.

La página muestra sola la versión, la fecha, el tamaño y las notas (en "Novedades de esta versión") del último Release. Escribe las notas en español y en texto plano, para quien instala la app: la página no interpreta Markdown. No hay que tocar el HTML ni volver a desplegar nada.

Enlace directo que siempre descarga la última versión:

```
https://github.com/tadeo77789/traducesenas-download/releases/latest/download/traducesenas.apk
```

## Estructura

| Archivo | Para qué |
|---|---|
| `index.html` | La página (HTML, CSS y JS en un solo archivo; textos en español, inglés, francés y portugués) |
| `assets/icono-senas.png` | Logo, copiado de `Frontend/src/assets/images/` |
| `.nojekyll` | Publica los archivos tal cual, sin procesarlos con Jekyll |

Idioma: se elige con el selector; también se puede forzar con `?lang=en` (o `es`, `fr`, `pt`).

## Activar GitHub Pages (una sola vez)

*Settings → Pages → Build and deployment*: **Deploy from a branch**, rama `main`, carpeta `/ (root)`.
