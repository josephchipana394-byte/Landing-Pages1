# ⚡ JYS Fast - Documentación Técnica y Estructura del Proyecto Web

Este repositorio contiene el código fuente de la plataforma web de **JYS Fast**, especializada en la difusión y comercialización de unidades de almacenamiento SSD NVMe y portátiles. 

El desarrollo se enfoca en una arquitectura frontend limpia, ligera y libre de librerías externas pesadas, construida desde cero con **HTML5 Semántico**, **CSS3 Modular (Tokens y Flex/Grid)** y **JavaScript ES6+**.

---

## 🛠️ Tecnologías y Arquitectura del Código

* **HTML5**: Uso estricto de marcado semántico para optimización de SEO y accesibilidad.
* **CSS3 Moderno**:
  * **Design Tokens (`:root`)**: Variables CSS para colores, sombras neón, transiciones y radios de borde.
  * **Sistema de Maquetación**: Combinación de **Flexbox** (para componentes dinámicos e hilera de navegación) y **CSS Grid** (para tarjetas de productos, testimonios y maquetación de FAQ).
  * **Efectos Neón & Micro-interacciones**: Transiciones fluidas a 60 FPS mediante `transform`, `opacity` y `box-shadow`.
  * **Diseño Adaptativo (Responsive)**: Uso de unidades dinámicas (`rem`, `%`, `vw`) y media queries para teléfonos, tablets y monitores.
* **JavaScript**: Manipulación ligera del DOM para lógica interactiva y conmutador de modo visual.

---

## 📂 Estructura de Archivos del Proyecto

```text
/
├── index.html        # Landing Page principal (Hero, Características, Galería, Testimonios, Contacto)
├── precios.html      # Módulo de Tarifas, Planes e Integración Comercial (WhatsApp)
├── faq.html          # Centro de Preguntas Frecuentes en Rejilla Asimétrica con Acordeones
├── style.css         # Hoja de estilos global, diseño modular, variables y responsive
├── script.js        # Lógica de componentes e interactividad
└── imagenes/         # Recursos vectoriales (SVG), fotos de productos y avatares


📐 Detalle Técnico por Archivo HTML y Reglas CSS
1. Página Principal (index.html)
Estructura HTML
Navegación (<header> + <nav>):

Menú superior persistente (Sticky) con logotipo vectorial enlazado al inicio.

Módulo de enlaces de navegación (<ul><li><a href="...">) y botón conmutador de tema visual.

Sección Hero (<section class="hero">):

Título principal (<h1>) con gradiente de color aplicado mediante CSS.

Resumen de propuesta de valor destacando la velocidad de hasta 7,300 MB/s.

Botón de llamada a la acción (CTA) con efectos de resplandor neón.

Módulo de Características (<section class="caracteristicas">):

Contenedor de tarjetas (<div class="cards">) alineado en rejilla.

4 Tarjetas (<article class="card">) para destacar los pilares clave:

Velocidad PCIe 5.0 (rayo.png)

Resistencia Militar IP67/IP68 (seguridad.png)

Cifrado Hardware AES 256-bits (candado.png)

Disipación Térmica de Nano-Grafeno (termometro.png)

Galería de Productos (<section class="galeria">):

Grilla de imágenes en alta definición con recortado proporcional (object-fit: cover).

Sección de Testimonios (<section class="testimonios">):

Bloques de opinión (<div class="testimonio">) con avatares circulares, nombres, cargos del cliente y valoración con estrellas SVG/FontAwesome.

Formulario de Contacto (<form id="contact-form">):

Entradas etiquetadas explícitamente (<label for="..."> e <input id="...">).

Selección de servicios mediante <select>.

Verificación obligatoria de términos con un <input type="checkbox">.

Reglas de Estilo CSS Aplicadas en style.css
Layout Flex/Grid: Los contenedores .cards y .galeria emplean display: grid con grid-template-columns: repeat(auto-fit, minmax(260px, 1fr)) para auto-ajuste responsive sin requerir múltiples media queries.

Efecto Hover en Tarjetas:

CSS
.card:hover {
    transform: translateY(-8px);
    box-shadow: var(--shadow-glow);
    border-color: var(--color-boton);
}



2. Módulo de Tarifas y Precios (precios.html)
Estructura HTML
Contenedor Principal de Tarifas (<section class="precios-container">):

Rejilla interactiva con 4 niveles de suscripción/planes:

Free ($0): Características esenciales para pruebas iniciales.

Starter ($9/mes): Para usuarios casuales y almacenamiento cotidiano.

Pro ($19/mes): Diseñado para creadores de contenido y editores de video.

Enterprise ($99/mes): Para infraestructuras corporativas y servidores.

Integración Comercial: Cada tarjeta posee un enlace directo a la API de WhatsApp (https://wa.me/...) preconfigurado con el nombre del plan elegido.

Sección de Clientes y Reseña Social (<section class="marcas">):

Rejilla de logotipos e instituciones que validan la calidad de las unidades de almacenamiento JYS Fast.

Reglas de Estilo CSS Aplicadas en style.css
Estilo de Tarjeta Destacada: La tarjeta del plan Pro/Enterprise cuenta con un borde especial de color neón y escala ligera (transform: scale(1.03)) para dirigir el ojo del usuario hacia la opción más rentable.



3. Centro de Ayuda y FAQ (faq.html)
Estructura HTML
Layout Asimétrico (<section class="faq-section">):

Lado izquierdo: Menú de navegación por categorías de consulta (General, Precios, Envíos, Soporte).

Lado derecho: Desplegables interactivos.

Acordeones Nativos (<details> y <summary>):

Utilización de elementos semánticos de HTML5 para abrir y cerrar respuestas sin sobrecargar el hilo de ejecución de JavaScript.

Reglas de Estilo CSS Aplicadas en style.css
Maquetación con grid-template-areas:

CSS
.faq-section {
    display: grid;
    grid-template-areas: 
        "sidebar content";
    grid-template-columns: 280px 1fr;
    gap: 2rem;
}
Personalización del Indicador de Desplegable: Estilos aplicados directamente sobre summary::-webkit-details-marker y transiciones suaves al expandir contenido.

🎨 Sistema de Diseño y Tokens CSS (:root)
Toda la coherencia estética del sitio se gestiona desde el bloque inicial de variables en style.css:

CSS
:root {
    /* Paleta de Colores Cyberpunk / Oscuro */
    --bg-primario: #0b0f19;         /* Fondo global de la aplicación */
    --bg-secundario: #111827;       /* Fondo de cabeceras y tarjetas */
    --color-texto: #f3f4f6;          /* Texto de alto contraste */
    --color-texto-mutado: #9ca3af;   /* Texto secundario y subtítulos */
    
    /* Colores de Acento y Neón */
    --color-boton: #00f2fe;         /* Neón cian principal */
    --color-boton-blue: #4facfe;    /* Azul secundario para gradientes */
    --border-color: #374151;        /* Borde sutil de contenedores */
    
    /* Efectos de Iluminación y Sombras */
    --shadow-glow: 0 0 20px rgba(0, 242, 254, 0.25);
    --shadow-card: 0 10px 15px -3px rgba(0, 0, 0, 0.3);
    
    /* Transiciones y Tiempos */
    --transition-fast: all 0.25s ease-in-out;
}
♿ Accesibilidad (a11y) y Estándares de Rendimiento
Navegación por Teclado:

Todos los botones, enlaces e hipervínculos cuentan con la pseudo-clase :focus-visible activa para mostrar un indicador neón cuando el usuario navega con la tecla Tab.

Textos Alternativos (alt):

Cada elemento <img> dentro del proyecto incluye descripciones detalladas sobre la función de la imagen o el producto representado.

Formularios Legibles:

Todos los controles de entrada (<input>, <select>, <textarea>) tienen etiquetas <label> vinculadas mediante sus atributos for e id correspondientes.
