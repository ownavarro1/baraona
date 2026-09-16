# Sitio de campaña — Rafael Baraona, Concejal de Montería

Sitio estático (HTML/CSS/JS puro, sin dependencias de build) con:
Hero, Propuestas, Sobre mí / Valores, Noticias (con video y carrusel de
prensa), Publicaciones de Facebook y Contacto.

## Cómo verlo localmente

Abre `index.html` directamente en el navegador, o sirve la carpeta con un
servidor simple para evitar restricciones de `file://`:

```
npx serve .
```

## Qué reemplazar antes de publicar

1. **Facebook** (`index.html`, sección `#noticias` y footer):
   - Cambia `data-href="https://www.facebook.com/facebook"` por la URL real
     de la página del candidato, ej. `https://www.facebook.com/RafaelBaraonaOficial`.
   - Cambia también los enlaces `href="https://www.facebook.com/facebook"`
     del botón "Ver página completa" y del ícono de Facebook en el footer.
   - Requisitos del Page Plugin: la página de Facebook debe ser pública
     (no de perfil personal) y tener contenido publicado; no requiere token
     ni revisión de app de Meta.

2. **Textos**: biografía completa, dirección exacta, correo y teléfono reales
   — busca los textos entre `[corchetes]` en `index.html`. Las fechas de las
   noticias también son placeholder.

3. **Fotos y video**: ya están integradas las fotos reales de la posesión en
   el Concejo de Montería (`img/foto-posesion-grupo.jpg`,
   `img/foto-rafael-discurso.jpg`) y el logo oficial (`img/logo-rafael-baraona.jpg`).
   El video de bienvenida vive en `video/bienvenida-concejo.mp4` (pesa ~11MB).
   - **Importante**: para producción, considera subir el video a YouTube o
     Facebook y embeberlo con `<iframe>` en vez de servirlo directo —
     evita cargar 11MB en cada visita y mejora la velocidad de carga móvil.
   - El logo tiene fondo blanco sólido (no transparente); por eso se muestra
     dentro de una insignia circular blanca en el header y footer. Si
     consigues una versión con fondo transparente (PNG), se verá aún mejor.

4. **Noticias**: las 3 tarjetas del carrusel son de ejemplo — reemplázalas
   con comunicados de prensa reales.

5. **Colores/marca**: todo el esquema de color vive en las variables CSS al
   inicio de `css/style.css` (`--color-navy`, `--color-gold`, `--color-red`, etc.).

6. **Formulario de contacto**: hoy solo muestra un aviso al enviarse (no
   guarda datos). Para que funcione de verdad, conéctalo a un servicio como
   Formspree/Getform, o a un backend propio.

## Siguientes pasos sugeridos

- Agregar páginas separadas (Biografía, Propuestas detalladas) si el
  contenido crece.
- Meta tags Open Graph (con el logo/foto) para que se vea bien al compartir
  en redes y WhatsApp.
- Analítica (Google Analytics / Meta Pixel) si la campaña lo requiere.
- Comprimir el video (ej. con HandBrake) antes de publicar, o migrarlo a
  YouTube/Facebook para no pesar el sitio.
