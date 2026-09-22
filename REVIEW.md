# Revisión de la web profesional

Fecha: 22 de septiembre de 2026.

## Alcance

Revisión del código y de las diez páginas en español e inglés, con comprobaciones en navegador a 320, 390, 768 y 1280 píxeles. Se revisaron contenido, jerarquía de títulos, navegación, imágenes, enlaces, metadatos y modo oscuro. No constituye una certificación completa de accesibilidad ni una medición de rendimiento con datos de visitantes reales.

## Problemas corregidos

- **Títulos principales ocultos.** Una regla CSS eliminaba visualmente los H1 de las páginas interiores y los retiraba del árbol de accesibilidad. Se eliminó: el tema ya evita duplicar el título de la portada.
- **Contraste insuficiente en modo oscuro.** El enlace secundario de la portada tenía una relación de contraste de 3,14:1. Ahora alcanza 8:1. También se ajustaron los enlaces del contenido y los estados activos de navegación. Referencia: [contraste mínimo en WCAG 2.2](https://www.w3.org/WAI/WCAG22/Understanding/contrast-minimum.html).
- **Separación de botones.** Markdown introducía un párrafo entre el contenedor flexible y los botones, impidiendo aplicar la separación prevista. La regla ahora actúa sobre ese párrafo.
- **Portada móvil.** Se redujo el espacio superior y se adaptó el tamaño del nombre para facilitar la lectura. La imagen declara sus dimensiones y prioridad de carga.
- **Organización del currículum.** La experiencia laboral aparece antes de los proyectos. Los proyectos conservan sus textos y enlaces, con encabezados y párrafos en lugar de una tabla ancha.
- **Idiomas y contacto.** Los controles del tema en inglés ya están traducidos. Los perfiles de contacto coinciden en ambos idiomas y los iconos del pie tienen nombres descriptivos.
- **Metadatos.** Las diez páginas tienen descripciones diferenciadas y metadatos Open Graph y Twitter para compartir enlaces. Se conservaron las URLs canónicas y alternativas de idioma.
- **Enlaces antiguos.** `/services/` y `/en/services/` redirigen a las competencias correspondientes mediante [mkdocs-redirects](https://github.com/mkdocs/mkdocs-redirects).
- **Publicación.** La compilación del despliegue utiliza `--strict`, que impide publicar si MkDocs detecta avisos.

## Verificación realizada

- Compilación estricta y comprobación de errores de formato de Git correctas.
- Las diez páginas tienen exactamente un H1, visible, el idioma esperado y una URL canónica correcta.
- Comprobación automática de enlaces internos, anclas, metadatos y ambas redirecciones.
- Las diez páginas no presentan desbordamiento horizontal a 320, 768 ni 1280 píxeles.
- Los 11 destinos externos únicos originales respondieron con HTTP 200; Twitter redirigía a X y se actualizó el enlace.
- Buscador probado con `FastAPI`; cambio de idioma probado conservando la página de experiencia.
- Comprobado el acceso por teclado al enlace para saltar al contenido.

## Mejoras que siguen siendo útiles

1. **Optimizar el archivo de la foto.** El JPEG original ocupa 1.756.150 bytes y mide 2268 × 4032 píxeles, aunque se muestra en un círculo de hasta 280 píxeles. Una copia optimizada para web reduciría la transferencia; se ha conservado el original sin modificar sus píxeles.
2. **Concretar resultados profesionales.** Algunas frases siguen siendo generales, especialmente la referencia a oportunidades de crecimiento. Conviene sustituirlas por aportaciones específicas y, cuando existan, resultados medidos y publicables. No se han inventado cifras ni responsabilidades.

## Mejoras completadas tras la revisión

- **CV descargable:** se incorporó el PDF actualizado facilitado por Enrique, sin modificarlo, con enlaces de descarga en la portada y en «Sobre mí» en ambos idiomas.
- **GitHub Actions:** actualizados [checkout a v7.0.1](https://github.com/actions/checkout/releases/tag/v7.0.1), [setup-uv a v10.2.0](https://github.com/astral-sh/setup-uv/releases/tag/v10.2.0), [upload-pages-artifact a v5.0.0](https://github.com/actions/upload-pages-artifact/releases/tag/v5.0.0) y [deploy-pages a v5.0.1](https://github.com/actions/deploy-pages/releases/tag/v5.0.1), fijados por SHA. Estas versiones utilizan Node 24, directamente o mediante la acción de subida de artefactos. Se fijaron Ubuntu 24.04, Python 3.12 y uv 0.12.17 para mantener un entorno predecible; la instalación respeta `uv.lock` con `--locked`.

La revisión reduce problemas conocidos; no implica que la web no pueda seguir mejorando ni verifica por sí sola la exactitud de títulos académicos, niveles de idiomas o toda la trayectoria laboral.
