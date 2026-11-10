# Todo a PDF

Conversor a PDF que funciona entero en el navegador: arrastra tus archivos, pulsa **Convertir ahora** y descarga el PDF. Nada se sube a ningún servidor.

## Qué convierte

| Formato | Extensiones | Resultado |
|---|---|---|
| Imágenes | PNG, JPG, WEBP, HEIC, GIF, BMP, SVG | Una página por imagen, en A4 o a su tamaño original |
| Word | DOCX | Conserva el diseño; el texto queda como imagen (no seleccionable) |
| Excel | XLSX, XLS, ODS, CSV | Una tabla por hoja con texto seleccionable; sin gráficos ni colores de celda |
| PowerPoint | PPTX | Una página por diapositiva: texto, imágenes, formas y tablas simples; sin gráficos ni efectos |
| Texto | TXT, MD | Texto limpio en A4 |
| PDF | PDF | Para unirlo con el resto en un solo documento |

También puede **unir todo en un solo PDF** (con el orden que elijas) o descargar todos en un `.zip`.

Los formatos antiguos `.doc` y `.ppt` no se convierten: guárdalos antes como `.docx` o `.pptx`.

## Publicarlo con GitHub Pages

1. Crea un repositorio nuevo en GitHub (por ejemplo `todo-a-pdf`) y sube estos archivos a la raíz.
2. En el repositorio: **Settings → Pages → Build and deployment**. En *Source* elige **Deploy from a branch**, rama **main**, carpeta **/ (root)**, y guarda.
3. En uno o dos minutos estará en `https://TU-USUARIO.github.io/todo-a-pdf/`.

En el móvil, abre esa dirección y usa **Añadir a pantalla de inicio** para tenerlo como una app.

## Archivos

- `index.html` — toda la herramienta (interfaz y conversores).
- `icon.svg` y `manifest.webmanifest` — icono y datos para instalarla en el móvil.

## Cómo funciona

No hay servidor ni instalación. La página carga estas librerías desde CDN solo cuando hacen falta, así que necesita conexión la primera vez que conviertes cada tipo de archivo:

- [pdf-lib](https://pdf-lib.js.org/) — crear y unir PDF
- [jsPDF](https://github.com/parallax/jsPDF) y [jspdf-autotable](https://github.com/simonbengtsson/jsPDF-AutoTable) — tablas y texto
- [SheetJS](https://sheetjs.com/) — leer Excel y CSV
- [docx-preview](https://github.com/VolodymyrBaydalka/docxjs) y [html2canvas](https://html2canvas.hertzen.com/) — Word
- [JSZip](https://stuk.github.io/jszip/) — leer PPTX y crear el `.zip`
- [heic2any](https://github.com/alexcorvi/heic2any) — fotos HEIC de iPhone
