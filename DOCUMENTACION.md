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

## 2. Investigación y análisis de usuarios

### 2.1 Datos demográficos y segmentación
El público objetivo de Kidwear se divide en dos segmentos principales:
* **Padres y madres jóvenes (28 a 42 años):** Usuarios habituales de smartphones, compran en momentos de descanso breve, trayectos o mientras atienden a sus hijos. Buscan rapidez, claridad en el stock y filtros automáticos por edad y temporada.
* **Compradores de regalos y abuelos (55 a 70 años):** Compran ropa infantil de forma puntual (cumpleaños, Navidad). Necesitan textos legibles, jerarquía visual evidente, botones táctiles generosos y asistencia directa para acertar la talla sin necesidad de conocer las medidas corporales exactas del menor.

### 2.2 Personas

#### Persona 1: Laura Morales (34 años) — Madre y compradora recurrente
* **Perfil:** Arquitecta y madre de dos niños (18 meses y 5 años). Compra habitualmente desde su smartphone con una sola mano mientras cuida de los pequeños o viaja en transporte público.
* **Objetivos:** Encontrar ropa cómoda y duradera rápidamente, filtrando por rango de edad exacto y completando la compra en dos minutos sin registros extensos.
* **Frustraciones:** Tablas de medidas complejas que exigen cinta métrica, procesos de compra con demasiados pasos y menús donde los botones son demasiado pequeños para pulsar con el pulgar.

#### Persona 2: Antonio Gómez (67 años) — Abuelo comprador de regalos
* **Perfil:** Jubilado, abuelo de una nieta de 4 años. Utiliza su móvil Android para mensajería y compras ocasionales.
* **Objetivos:** Comprar un conjunto infantil para el cumpleaños de su nieta con la seguridad de que le servirá de talla, identificando con claridad el precio final y los pasos a seguir.
* **Frustraciones:** Textos pequeños con bajo contraste, interfaces oscuras poco legibles, temor a equivocarse en el cobro y falta de mensajes claros de confirmación al terminar un pedido.

### 2.3 Análisis de la competencia

| Competidor | Qué hace bien | Qué hace mal | Qué nos llevamos para Kidwear |
|---|---|---|---|
| **Mayoral** | Excelente categorización por tramos de meses y años en catálogo. | Interfaz móvil muy recargada, con demasiados banners publicitarios y botones pequeños. | Estructuración directa de categorías por edad (0-24 m, Niña, Niño) manteniendo un diseño visual limpio. |
| **Zara Kids** | Fotografía de producto cuidada y diseño moderno y minimalista. | Contraste tipográfico deficiente en fichas de producto; selector de talla poco intuitivo para no iniciados. | Ficha de producto enfocada en imágenes claras, pero garantizando contraste alto (WCAG AA ≥ 4,5:1) y botones táctiles evidentes. |
| **H&M Kids** | Guía de tallas interactiva con equivalencias de altura y peso. | Proceso de checkout excesivamente largo con formularios densos que saturan en pantalla pequeña. | Guía de tallas accesible en un solo clic mediante *bottom sheet* desplegable, sin perder el contexto del producto. |

### 2.4 Insights y hallazgos clave
1. **Uso con una sola mano en movimiento:** Los usuarios sostienen el teléfono con el pulgar mientras sujetan a sus hijos o bolsas.  
   * *Decisión de diseño:* Situar los botones principales de acción (*Call to Action*) y la barra de navegación en el tercio inferior de la pantalla, con áreas táctiles mínimas de 48×48 dp.
2. **Incertidumbre crítica con el tallaje:** La principal causa de abandono y devolución es no saber qué talla equivale a la edad real del niño.  
   * *Decisión de diseño:* Integrar un botón directo «Guía de tallas» en la ficha de producto que abre un *bottom sheet* contextual con rangos de edad y altura en centímetros.
3. **Miedo al cobro accidental o error en el pedido:** Compradores mayores y personas con prisa necesitan certidumbre total de lo que ocurre con su dinero.  
   * *Decisión de diseño:* Pantalla de confirmación con número de pedido, resumen del importe y opción de deshacer (*Snackbar*) ante acciones críticas como eliminar artículos del carrito.
4. **Sobrecarga cognitiva en la búsqueda:** Las categorías genéricas de adultos ("Pantalones", "Camisas") no sirven; los padres compran según la etapa de crecimiento.  
   * *Decisión de diseño:* Pantalla de inicio estructurada con accesos prioritarios por tramos de edad (*Bebés*, *Peques*, *Grandes*) y *filter chips* combinables en el catálogo.

   ## 3. Diseño de la interfaz

### 3.1 Mapa de navegación

A continuación se representa la arquitectura de la información y el flujo de navegación principal, que incluye las siete pantallas obligatorias y los componentes modales interactivos:

```mermaid
flowchart TD
    %% Destinos principales de la barra de navegación
    subgraph Nav[Barra de navegación]
        Inicio[01 - Inicio]
        Catalogo[02 - Catálogo]
        Perfil[07 - Perfil]
    end

    %% Flujo principal de compra
    Inicio -->|Explorar catálogo| Catalogo
    Catalogo -->|Seleccionar producto| Detalle[03 - Detalle de producto]
    Detalle -->|Añadir al carrito| Carrito[04 - Carrito]
    Carrito -->|Tramitar pedido| Checkout[05 - Checkout]
    Checkout -->|Pagar| Confirmacion[06 - Confirmación]

    %% Acciones tras la compra
    Confirmacion -.->|Seguir comprando| Inicio
    Confirmacion -.->|Ver mis pedidos| Perfil
```

### 3.2 Wireframes

A continuación se presentan los wireframes de baja fidelidad en escala de grises diseñados para una resolución base de 360×800 dp (Android Compact):

#### 01. Inicio
![01 - Inicio](capturas/wireframes/01%20-%20Inicio.png)

#### 02. Catálogo
![02 - Catálogo](capturas/wireframes/02%20-%20Catalogo.png)

#### 03. Detalle del producto
![03 - Detalle del producto](capturas/wireframes/03%20-%20Detalle.png)

#### 04. Carrito
![04 - Carrito](capturas/wireframes/04%20-%20Carrito.png)

#### 05. Checkout
![05 - Checkout](capturas/wireframes/05%20-%20Checkout.png)

#### 06. Confirmación
![06 - Confirmación](capturas/wireframes/06%20-%20Confirmacion.png)

#### 07. Perfil
![07 - Perfil](capturas/wireframes/07%20-%20Perfil.png)

### 3.3 Guía de estilo Material Design 3

El sistema visual de «Kidswear» implementa los estándares de **Material Design 3 (M3)**. Todos los tokens técnicos (esquemas de color, tipografía y métricas espaciales) se encuentran centralizados en el archivo `diseno/estilos.json`.

#### 1. Sistema cromático y color semilla
* **Color semilla (*Source Color*):** `#B85D43` (Terracota cálido).
  * **Justificación:** Se seleccionó un tono terracota cálido para transmitir cercanía, confort y modernidad, propio de las marcas contemporáneas de moda infantil y calzado, evitando colores sobresaturados convencionales y cumpliendo la pauta de prescindir de tonos verdes.
* **Tokens semánticos de color:**
  * **Modo Claro (*Light Theme*):** `primary`: `#8F4B38`, `onPrimary`: `#FFFFFF`, `primaryContainer`: `#FFDBD1`, `onPrimaryContainer`: `#723523`, `secondary`: `#77574E`, `onSecondary`: `#FFFFFF`, `tertiary`: `#6C5D2F`, `onTertiary`: `#FFFFFF`, `surface`: `#FFF8F6`, `onSurface`: `#231917`, `error`: `#BA1A1A`, `onError`: `#FFFFFF`.
  * **Modo Oscuro (*Dark Theme*):** `primary`: `#FFB5A0`, `onPrimary`: `#561F0F`, `primaryContainer`: `#723523`, `onPrimaryContainer`: `#FFDBD1`, `secondary`: `#E7BDB2`, `onSecondary`: `#442A22`, `tertiary`: `#D9C58D`, `onTertiary`: `#3B2F05`, `surface`: `#1A110F`, `onSurface`: `#F1DFDA`, `error`: `#FFB4AB`, `onError`: `#690005`.

#### 2. Auditoría de contraste y accesibilidad (WCAG 2.1 AA)
De acuerdo con las pautas WCAG 2.1, todo elemento interactivo o de texto debe superar el contraste mínimo de **4.5:1** (nivel AA) y **3.0:1** en componentes gráficos. Se han verificado las 12 parejas `color` / `on-color`:

| Esquema | Pareja de color | Código Color | Código On-Color | Ratio de contraste | Cumplimiento WCAG |
| :--- | :--- | :---: | :---: | :---: | :---: |
| **Claro** | `primary` / `onPrimary` | `#8F4B38` | `#FFFFFF` | **6.50:1** | Supera AA (mín. 4.5:1) |
| **Claro** | `primaryContainer` / `onPrimaryContainer` | `#FFDBD1` | `#723523` | **7.25:1** | Cumple AAA (mín. 7.0:1) |
| **Claro** | `secondary` / `onSecondary` | `#77574E` | `#FFFFFF` | **6.45:1** | Supera AA (mín. 4.5:1) |
| **Claro** | `tertiary` / `onTertiary` | `#6C5D2F` | `#FFFFFF` | **6.47:1** | Supera AA (mín. 4.5:1) |
| **Claro** | `surface` / `onSurface` | `#FFF8F6` | `#231917` | **16.36:1** | Cumple AAA (mín. 7.0:1) |
| **Claro** | `error` / `onError` | `#BA1A1A` | `#FFFFFF` | **6.46:1** | Supera AA (mín. 4.5:1) |
| **Oscuro** | `primary` / `onPrimary` | `#FFB5A0` | `#561F0F` | **7.74:1** | Cumple AAA (mín. 7.0:1) |
| **Oscuro** | `primaryContainer` / `onPrimaryContainer` | `#723523` | `#FFDBD1` | **7.25:1** | Cumple AAA (mín. 7.0:1) |
| **Oscuro** | `secondary` / `onSecondary` | `#E7BDB2` | `#442A22` | **7.70:1** | Cumple AAA (mín. 7.0:1) |
| **Oscuro** | `tertiary` / `onTertiary` | `#D9C58D` | `#3B2F05` | **7.73:1** | Cumple AAA (mín. 7.0:1) |
| **Oscuro** | `surface` / `onSurface` | `#1A110F` | `#F1DFDA` | **14.42:1** | Cumple AAA (mín. 7.0:1) |
| **Oscuro** | `error` / `onError` | `#FFB4AB` | `#690005` | **7.72:1** | Cumple AAA (mín. 7.0:1) |

#### 3. Rejilla y sistema espacial (*Layout Grid*)
* **Columnas:** 4 columnas fluidas en disposición móvil con medianil (*gutter*) de 16 dp.
* **Márgenes de pantalla:** 16 dp en los bordes laterales del dispositivo.
* **Malla modular:** Múltiplos de 8 dp para espaciados, rellenos (*padding*) y dimensiones estructurales (con paso de 4 dp para ajustes finos).
* **Áreas táctiles mínimas:** Todos los componentes interactivos respetan el área mínima de **48×48 dp**, garantizando la operabilidad táctil accesible y ergonómica.

### 3.4 Prototipo de alta fidelidad

En esta fase se ha desarrollado el prototipo interactivo de alta fidelidad para la aplicación móvil de comercio electrónico de moda infantil, materializando los wireframes iniciales en una interfaz visual definitiva y funcional mediante **Figma**.

#### 1. Especificaciones técnicas y estándares de diseño
* **Resolución base:** 360 × 800 px (estándar de referencia para dispositivos móviles compactos y directrices de Material Design 3).
* **Sistema de diseño:** Implementación integral de los principios de **Material Design 3 (M3)** utilizando roles y tokens semánticos generados mediante *Material Theme Builder*.
* **Jerarquía tipográfica y espacial:** Retícula de 4/8 dp, esquinas redondeadas en tarjetas y componentes interactivos según la escala de redondeo M3 (*Large* y *Medium* shape tokens), e iconografía basada en *Material Symbols*.
* **Roles de color aplicados:**
  * `Primary` y `On Primary`: Acentos y botones principales de llamada a la acción (CTA).
  * `Surface`, `Surface Container` y `Surface Container High`: Capas de profundidad para fondos y tarjetas de producto.
  * `On Surface` y `On Surface Variant`: Contraste tipográfico accesible para títulos y textos secundarios.
  * `Error` (`#BA1A1A`) y `On Error`: Notificaciones y validaciones en estados críticos de la interfaz.

---

#### 2. Flujo de navegación e interacciones implementadas
El prototipo cubre el ciclo de compra de extremo a extremo (*end-to-end*), contemplando tanto el camino habitual (*happy path*) como escenarios alternativos y de control de errores:

1. **Pantalla de Inicio (`01`):** Búsqueda directa, navegación rápida por categorías de edad (*Bebés, Peques, Grandes*) y carrusel de novedades con acceso a detalle de producto.
2. **Catálogo (`02`):** Vista de rejilla de productos con filtros y navegación estructurada.
3. **Detalle de producto (`03`):** 
   * Selector interactivo de tallas con cambio dinámico de estado (ej. cambio a talla *6M*).
   * Estado inactivo y estado deshabilitado (*disabled*) para tallas agotadas (*24M*), aplicando atenuación al 38% de opacidad según directrices de accesibilidad.
   * Apertura de la **Guía de tallas** mediante ventana modal superpuesta (*overlay*).
4. **Carrito de compra (`04`):** Resumen de artículos seleccionados, desglose de importes y botón de tramitación.
5. **Checkout y gestión de errores (`05` y `05b`):** 
   * Selección de métodos de pago (Tarjeta de crédito / Bizum).
   * Documentación del **estado de error (`05b`)**: tratamiento de denegación de pago con token semántico de error, borde de advertencia y mensaje de recuperación contextual.
6. **Confirmación de pedido (`06`):** Notificación de compra satisfactoria con número de pedido y botón de retorno al inicio.
7. **Perfil de usuario (`07`):** Gestión de cuenta, direcciones y pedidos.

---

#### 3. Soporte para Modo Oscuro (Dark Theme)
Se han diseñado las variantes en modo oscuro para las pantallas centrales de navegación (**Inicio** y **Detalle**), asegurando:
* Reducción de fatiga visual mediante superficies oscuras neutras/cálidas (`Surface Dark`), evitando el uso de negros puros absolutos.
* Recalibración del token `Primary` a un tono de mayor luminancia (Tono 80 / `#FFB5A0`) para mantener el ratio de contraste reglamentario (WCAG AA/AAA) sobre fondos oscuros.
* Adaptación de los chips interactivos (tallas inactivas con contornos en `Outline Variant` y chip agotado atenuado).

## 4. Validación y pruebas

### 4.1 Metodología
Para evaluar la usabilidad y la coherencia del flujo de navegación en el prototipo interactivo (360 × 800 px), se definieron tres tareas representativas sin asistencia guiada, evaluando tres métricas clave:
* **Tasa de éxito:** Finalización autónoma de la tarea sin asistencia.
* **Tiempo:** Segundos requeridos para completar cada acción.
* **Errores:** Clics fallidos, interacciones erróneas o desorientación en el flujo.

#### Tareas evaluadas:
1. **Tarea 1 (Navegación y selección):** Localizar el «Conjunto Bebé» desde la pantalla de inicio, entrar al detalle y seleccionar la talla **6M**.
2. **Tarea 2 (Consulta de modal/overlay):** Abrir el enlace de la **«Guía de tallas»**, consultar las medidas en la ventana superpuesta y cerrarla para volver a la prenda.
3. **Tarea 3 (Flujo completo de compra):** Añadir el producto al carrito, acceder a la cesta para revisar el importe y completar la tramitación del pedido (*checkout*) hasta llegar a la pantalla de confirmación.

---

### 4.2 Resultados
Se realizaron las pruebas con dos participantes (Alberto y Laura), obteniendo los siguientes resultados:

| Tarea | Métrica | Participante 1 | Participante 2 | Media / Global |
| :--- | :--- | :---: | :---: | :---: |
| **T1: Búsqueda y selección talla 6M** | Éxito<br>Tiempo<br>Errores | **100%**<br>14 s<br>0 | **100%**<br>18 s<br>0 | **100% éxito**<br>16,0 s<br>0 errores |
| **T2: Consulta Guía de tallas (Overlay)** | Éxito<br>Tiempo<br>Errores | **100%**<br>9 s<br>0 | **100%**<br>12 s<br>1 | **100% éxito**<br>10,5 s<br>0,5 errores |
| **T3: Carrito y confirmación de compra** | Éxito<br>Tiempo<br>Errores | **100%**<br>21 s<br>0 | **100%**<br>19 s<br>0 | **100% éxito**<br>20,0 s<br>0 errores |

* **Observaciones clave:**
  * La navegación principal de compra (T3) resultó fluida y directa desde el detalle hasta la pantalla de confirmación, sin desvíos ni dudas en el botón de pago.
  * En T2, un participante intentó cerrar la guía de tallas haciendo clic en el área oscurecida exterior en vez del botón de cierre.
  * **Validación de la pantalla de error (`05b`):** Al documentarse como estado estático independiente para evitar solapamientos de interacción en el prototipo interactivo, se evaluó mediante inspección visual. Ambos participantes identificaron de inmediato la denegación del pago gracias al token semántico de error (`#BA1A1A`) y al mensaje contextual.

---

### 4.3 Iteraciones y mejoras

A partir de los resultados obtenidos en las pruebas con usuarios (específicamente la fricción detectada en la Tarea 2 relativa al cierre del diálogo superpuesto), se aplicó una iteración de diseño sobre el modal de la **Guía de tallas**:

#### 1. Diagnóstico del problema
* **Fricción detectada:** El modal original disponía únicamente de un icono de aspa («X») en la esquina superior derecha. En una pantalla móvil de 360 × 800 px, esa zona queda fuera de la zona ergonómica del pulgar para el uso con una sola mano. Además, el fondo oscurecido (*scrim*) no permitía el cierre táctil directo.

#### 2. Solución implementada (Material Design 3)
* **Botón de acción accesible:** Se incorporó un botón centrado en la parte inferior con la etiqueta **«Cerrar»** (*Filled Tonal Button*, altura táctil de 40 dp, bordes redondeados y estilos de color `Primary Container` / `On Primary Container`), situando la acción de salida en la zona cómoda de interacción.
* **Cierre por toque exterior:** Se configuró en el prototipo interactivo de Figma la opción *«Close when clicking outside»*, permitiendo descartar el modal al tocar cualquier punto fuera de la tarjeta.

---

#### 3. Comparativa Antes y Después

| Antes | Después |
| :---: | :---: |
| ![Antes](capturas/iteracion/antes.png) | ![Después](capturas/iteracion/despues.png) |
| *Modal inicial con un único punto de cierre superior.* | *Modal optimizado con botón inferior táctil y cierre al tocar fuera.* |

## 5. Entrega y documentación final

### 5.1 Justificación del diseño propuesto

La solución de diseño desarrollada para la aplicación de moda infantil responde a criterios de usabilidad, ergonomía móvil y coherencia visual basados en el marco de trabajo de **Material Design 3 (M3)**:

* **Enfoque centrado en el usuario y contexto de uso:**  
  El público objetivo (madres, padres y cuidadores) requiere realizar compras de forma rápida, habitualmente usando el móvil con una sola mano. Por ello, la disposición de elementos respeta la «zona del pulgar» (*thumb zone*), ubicando los botones de acción primarios (*Primary CTA*), la navegación por pestañas y los controles de selección de tallas en las zonas medias e inferiores de la pantalla (360 × 800 px).

* **Sistema de diseño y tokens semánticos (M3):**  
  El uso de roles semánticos en lugar de valores hexadecimales aislados garantiza consistencia en todos los flujos. La paleta generada mediante *Material Theme Builder* equilibra tonos cálidos propios del sector infantil con contrastes accesibles:
  * El color `Primary` dirige la atención hacia las acciones de conversión (añadir a la cesta, tramitar pedido).
  * Los contenedores `Surface` y `Surface Container` estructuran la información en capas jerárquicas claras sin sobrecargar visualmente la pantalla.
  * Los estados de error (`Error` / `#BA1A1A`) y deshabilitado (tallas agotadas con 38% de opacidad) reducen la carga cognitiva y evitan frustración en la selección de producto.

* **Soporte Dark Theme y accesibilidad:**  
  La adaptación a modo oscuro no invierte colores arbitrariamente; redistribuye la luminancia para mantener el cumplimiento de contraste según los criterios de éxito WCAG 2.1 (nivel AA), reduciendo la fatiga visual en entornos de baja iluminación.

---

### 5.2 Recomendaciones y pasos a seguir

Tras el ciclo de diseño, prototipado interactivo e iteración de usabilidad, se proponen las siguientes fases para la evolución técnica del producto:

1. **Transferencia a desarrollo (*Design Handoff*):**  
   * Exportar los tokens de diseño (colores, tipografía y radios) a formatos estructurados (como JSON de *Style Dictionary*) para su consumo directo en desarrollo móvil nativo (Jetpack Compose o Flutter).
   * Definir las especificaciones de espaciado y retícula basadas en múltiplos de 4/8 dp para facilitar el maquetado.

2. **Microinteracciones y feedback del sistema:**  
   * Incorporar componentes *Snackbar* o alertas flotantes con retroalimentación inmediata tras añadir artículos a la cesta antes de dirigir al usuario al carrito.
   * Implementar estados de carga esqueleto (*Skeleton loaders*) en las vistas de catálogo e inicio para mejorar el rendimiento percibido durante peticiones de red.

3. **Pruebas de accesibilidad avanzadas:**  
   * Ejecutar auditorías de accesibilidad con lectores de pantalla móviles (TalkBack en Android y VoiceOver en iOS) para validar el etiquetado semántico de los botones de tallas y diálogos modales.

4. **Analítica y pruebas de conversión en producción:**  
   * Medir métricas de abandono en el embudo de *checkout* y evaluar mediante tests A/B el rendimiento de distintos métodos de pago simplificados (como pasarelas nativas tipo Google Pay o Apple Pay).

## 6. Referencias bibliográficas

Google. (2021). *Material Design 3: The next evolution of Material Design*. Material Design. https://m3.material.io/

Hoober, S. (2013, 18 de febrero). *How do users really hold mobile devices?* UXmatters. https://www.uxmatters.com/mt/archives/2013/02/how-do-users-really-hold-mobile-devices.php

Nielsen, J., & Budiu, R. (2013). *Mobile usability*. New Riders. https://www.nngroup.com/books/mobile-usability/

World Wide Web Consortium. (2018). *Web Content Accessibility Guidelines (WCAG) 2.1* (W3C Recommendation). W3C. https://www.w3.org/TR/WCAG21/


Palabra del día: 29