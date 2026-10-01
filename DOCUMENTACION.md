# Documentación de la interfaz — Kidwear

## 1. Justificación del diseño

### 1.1 Importancia del diseño centrado en el usuario
Kidwear es una cadena de tiendas físicas de ropa y calzado infantil (0 a 14 años) que aborda su primer canal móvil Android. Su público principal está compuesto por madres, padres, abuelos y compradores de regalos. Este perfil se caracteriza por:
* Disponer de poco tiempo libre.
* Manejar el dispositivo habitualmente con una sola mano mientras atienden a sus hijos o realizan otras tareas simultáneas.
* Experimentar una alta incertidumbre a la hora de seleccionar tallas debido al rápido crecimiento de los niños y la disparidad entre marcas.

Aplicar el diseño centrado en el usuario (DCU) y los estándares de Material Design 3 garantiza una interfaz ergonómica, con botones dentro del alcance del pulgar, áreas táctiles amplias (mínimo 48×48 dp) y herramientas directas que resuelvan la duda de la talla antes de formalizar la compra, reduciendo la fricción y el abandono del carrito.

### 1.2 Objetivos y metas del proyecto
1. **Eficiencia en la compra:** Permitir que un usuario localice una prenda, elija su talla y complete el flujo de compra en menos de **2 minutos (120 segundos)**.
2. **Reducción de dudas con el tallaje:** Lograr que más del **85% de los usuarios** seleccione la talla correcta sin abandonar la ficha de producto, apoyados por una guía de tallas accesible en un solo toque mediante bottom sheet.
3. **Ergonomía y accesibilidad:** Conseguir una tasa de éxito superior al **90% en navegación con una sola mano**, asegurando que todas las acciones críticas cumplan el estándar de área táctil mínima de **48×48 dp** y contraste visual **WCAG AA (≥ 4,5:1)**.

### 1.3 Beneficios esperados
* **Para el usuario:** Confianza inmediata al seleccionar tallas, rapidez en compras rutinarias y un proceso de pago guiado y claro, accesible tanto para usuarios digitales habituales como para abuelos menos familiarizados con compras móviles.
* **Para el negocio:** Incremento en la tasa de conversión móvil, fidelización del cliente físico en el entorno digital y reducción drástica de costes logísticos derivados de devoluciones y cambios por error de talla.

