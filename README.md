# 🌐 AI Insights — IA Lab Web Architecture

[![HTML5](https://img.shields.io/badge/HTML5-Semantic%20Markup-E34F26.svg?style=flat-square&logo=html5&logoColor=white)](https://developer.mozilla.org/es/docs/Web/HTML)
[![Sass/SCSS](https://img.shields.io/badge/Sass-SCSS%20Theming-CC6699.svg?style=flat-square&logo=sass&logoColor=white)](https://sass-lang.com)
[![JavaScript](https://img.shields.io/badge/JavaScript-ES6+-F7DF1E.svg?style=flat-square&logo=javascript&logoColor=black)](https://developer.mozilla.org/es/docs/Web/JavaScript)
[![Course](https://img.shields.io/badge/Course-Inform%C3%A1tica%20II%20(UNAM)-002B49.svg?style=flat-square)](https://www.cuautitlan.unam.mx/)
[![License](https://img.shields.io/badge/License-MIT-green.svg?style=flat-square)](./LICENSE)
[![Author](https://img.shields.io/badge/Author-Ian%20Miguel%20Huitron-007acc.svg?style=flat-square)](https://github.com/iamhuitron)
[![Studio](https://img.shields.io/badge/Studio-XAOL%20Software%20Studio-blueviolet.svg?style=flat-square)](https://github.com/Xaol-Studio)

Portal web educativo y plataforma de divulgación técnica orientada a la exploración de **Inteligencia Artificial, Machine Learning y Ética Tecnológica**. Desarrollado como proyecto para la cátedra de **Informática II** en la UNAM FES Cuautitlán.

---

## 📑 Tabla de Contenidos

- [Descripción del Proyecto](#-descripción-del-proyecto)
- [Arquitectura de Estilos y SCSS](#-arquitectura-de-estilos-y-scss)
- [Pipeline de Optimización de Activos](#-pipeline-de-optimización-de-activos)
- [Componentes Interactivos](#-componentes-interactivos)
- [Estructura del Proyecto](#-estructura-del-proyecto)
- [Páginas y Vistas Disponibles](#-páginas-y-vistas-disponibles)
- [Despliegue Local](#-despliegue-local)
- [Licencia](#-licencia)

---

## 📌 Descripción del Proyecto

AI Insights unifica contenidos formativos, análisis de aplicaciones prácticas de modelos generativos y proyectos de visión artificial en una interfaz responsiva, accesible y orientada al usuario.

El sistema fue diseñado priorizando:
- **Semántica web rigurosa:** Encabezados jerárquicos, etiquetas estructurales (`<main>`, `<nav>`, `<article>`, `<section>`), y enlaces de salto para accesibilidad (`skip-link`).
- **Arquitectura de diseño modular:** Variables centralizadas de color y espaciado que sobrescriben y personalizan el sistema de cuadrícula Bootstrap a través de Sass (`style.scss`).
- **Rendimiento visual:** Flujo automatizado de conversión a formatos de compresión moderna de última generación (`.webp`).

---

## 🎨 Arquitectura de Estilos y SCSS

El proyecto organiza sus reglas en [`scss/style.scss`](./scss/style.scss), importando la biblioteca Sass completa de Bootstrap 4 y personalizando variables clave:

```scss
/******* Bootstrap Theming ********/
$primary: #FFC600;       // Amarillo de acento AI Lab
$secondary: #23A036;     // Verde de validación
$light: #F5F5F5;         // Fondo claro neutro
$dark: #0a1026;          // Azul marino profundo para tipografía y headers

$font-family-sans-serif: 'Poppins', sans-serif;
$enable-responsive-font-sizes: true;
$border-radius: 5px;

@import "bootstrap/scss/bootstrap";
```

### Compilación de SCSS
Si deseas recompilar la hoja de estilos tras realizar ajustes:
```bash
sass scss/style.scss css/style.css --style compressed
```

---

## 🖼️ Pipeline de Optimización de Activos

El directorio [`scripts/`](./scripts/) incluye la herramienta automatizada [`convert-images.sh`](./scripts/convert-images.sh), que decodifica representaciones Base64 de alta resolución y genera imágenes responsivas con soporte `srcset` en resoluciones 400px, 800px y 1600px, produciendo tanto copias JPG como variantes WebP optimizadas:

```bash
chmod +x scripts/convert-images.sh
./scripts/convert-images.sh
```

---

## ⚡ Componentes Interactivos

- **Animación de métricas:** Contadores numéricos dinámicos al hacer scroll (`data-toggle="counter-up"`).
- **Navegación inteligente:** Menús desplegables activados por hover en desktop con soporte táctil en dispositivos móviles.
- **Lightbox y Carousels:** Visualización de galerías de proyectos y testimonios mediante `Owl Carousel` y `Lightbox2`.
- **Canal de contacto:** Validación asíncrona de formularios del lado del cliente (`jqBootstrapValidation`) con handler PHP en [`mail/contact.php`](./mail/contact.php).

---

## 🗂️ Estructura del Proyecto

```
ai-insights/
├── index.html                      # Página de inicio y resumen de áreas
├── about.html                      # Misión, visión e historia del laboratorio
├── service.html                    # Líneas de investigación y servicios de IA
├── project.html                    # Galería interactiva de casos de estudio
├── blog.html                       # Artículos divulgativos y análisis
├── single.html                     # Detalle de publicación de blog
├── css/
│   └── style.css                   # CSS compilado y optimizado
├── scss/
│   ├── style.scss                  # Definición de variables y temas
│   └── bootstrap/                  # Fuentes modulares SCSS de Bootstrap
├── js/
│   └── main.js                     # Controladores UI, scroll y eventos
├── mail/
│   ├── contact.js                  # Manejador AJAX de formulario
│   └── contact.php                 # Endpoint de entrega de correos
├── scripts/
│   └── convert-images.sh           # Script de procesamiento de imágenes
└── README.md
```

---

## 🚀 Despliegue Local

Al tratarse de una arquitectura orientada a la web moderna, no requiere compiladores pesados para su visualización:

### Con Python (Recomendado)
```bash
python3 -m http.server 8000
```
Navega a `http://localhost:8000`.

### Con PHP (para habilitar el formulario de contacto)
```bash
php -S localhost:8000
```

---

## 📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo [LICENSE](./LICENSE) para más detalles.

