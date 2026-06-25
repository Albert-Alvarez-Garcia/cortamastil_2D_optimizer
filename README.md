🪵 CortaMástil // OPTIMIZADOR 2D

CortaMástil es un optimizador de despiece bidimensional (algoritmo de Nesting) de estética industrial brutalista, diseñado para aficionados al bricolaje y profesionales de la madera. Permite calcular la distribución óptima de múltiples piezas sobre tableros estándar, gestionando mermas de corte y evaluando si los paneles resultantes caben físicamente en el maletero de tu coche.

[!IMPORTANT]
El proyecto está construido como un Single-Page Application (SPA) puro. Todo el motor de cálculo, la lógica logística de transporte, los mapas vectoriales y la interfaz residen en un único archivo HTML autocontenido. Sin dependencias externas pesadas, sin bases de datos y diseñado para funcionar de manera offline.

📸 Vista Previa del Panel

El panel principal unifica la configuración paramétrica, el despiece tipado, la simulación interactiva y el reporte de conflictos físicos en tiempo real.

✨ Características Principales

⚡ Algoritmo de Nesting Optimizado: Implementa una variante del empaquetado voraz (Greedy Bin Packing) en $O(n \log n)$ que prioriza la colocación de piezas por área decreciente con soporte para rotación dinámica.

📐 Gestión de Merma Real ($m$): Introduce el grosor exacto de la hoja de corte (caladora de $1.5\text{ mm}$, sierra de mano de $3.0\text{ mm}$ o disco industrial de $4.0\text{ mm}$) para descontar la pérdida de material por cada pasada en la subdivisión de espacios.

🚗 Control de Habitáculo 3D (Alertas de Coche): Evalúa geométricamente si cada pieza cabe en el maletero utilizando tres orientaciones espaciales posibles según las cotas de carga configuradas (ej: $1000 \times 800 \times 1500\text{ mm}$).

✂️ Subdivisiones Simétricas de Seguridad: Si una pieza excede los límites de transporte, el sistema activa una alerta visual interactiva que permite dividirla por su eje simétrico con un solo clic.

💾 Persistencia Local (JSON): Exporta e importa proyectos completos en formato .json sin perder el listado de piezas, las cantidades ni las mermas.

📋 Hojas de Ruta Imprimibles (PDF): Un sistema de estilos @media print redibuja mapas vectoriales limpios sobre fondos neutros con el listado preciso de coordenadas iniciales $(X, Y)$ para cada operario.

📋 Hojas de Ruta de Corte Generadas

El sistema genera hojas técnicas independientes para cada tablero empleado, mostrando la eficiencia de aprovechamiento del material (ej: $75.5\%$ de área útil) y las directrices exactas de corte.

Hoja de Ruta - Tablero $1$ (Despiece General)

Hoja de Ruta - Tablero $2$ (Subdivisiones)





🚀 Instalación y Uso

Al ser un desarrollo estático autocontenido, no necesitas procesos de compilación ni servidores locales:

Clona este repositorio en tu máquina:

git clone https://github.com/Albert-Alvarez-Garcia/cortamastil_2D_optimizer.git


Abre el archivo index.html en tu navegador web preferido (Chrome, Firefox, Safari, Edge).

¡Empieza a optimizar tus planchas de madera de forma inmediata!

🛠️ Arquitectura Técnica

Tecnologías: HTML5, CSS3 y Vanilla JavaScript.

Framework CSS: Tailwind CSS (inyectado a través de CDN oficial con configuración activa de modo oscuro).

Renderizado: Canvas API bidimensional con escalado relacional dinámico basado en el aspect-ratio del tablero base (ej: $2440 \times 1220\text{ mm}$).

Algoritmo: Basado en la subdivisión geométrica recursiva de espacios vacíos tras cada inserción, garantizando la detección del espacio sobrante para el posterior análisis manual de retales.

📄 Licencia

Este proyecto está bajo la Licencia MIT. Consulta el archivo LICENSE para más detalles.

Desarrollado bajo el paradigma brutalista: código utilitario, tipografía monospace y rendimiento sin concesiones.
