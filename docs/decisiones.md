# Documento de decisiones de diseño

> Cada decisión: **qué** elegiste, **por qué**, y **qué alternativa descartaste**.
> Se evalúa la justificación, no la longitud. Máximo 2 páginas en la Fase 1.

## Ruta de trabajo

- [ ] Ruta A · Figma
- [x] Ruta B · VS Code (diseño directamente en `guia.html`)

## 1. Color (RA1 · CE b)

- Tono de acento: 82°, según la ficha del caso 09. Se ha elegido una escala cálida dorada, variando la luminosidad para disponer de tonos claros, intermedios y oscuros.
- Acento claro: `acento-700` (#855a00), porque ofrece contraste suficiente sobre superficies claras.
- Acento oscuro: `acento-400` (#d4a64c), porque mantiene la identidad dorada y ofrece contraste suficiente en superficies oscuras.
- Tokens semánticos: fondo, superficie, texto, texto-suave, borde, borde-control, acento, acento-hover, sobre-acento, acento-tenue, exito, exito-tenue y foco.
- Pares de contraste: se mantienen los pares definidos en `$pares-contraste`, comprobados automáticamente por Sass en los dos temas.

## 2. Tipografía (RA1 · CE b)

- Familia elegida: system-ui para el texto general. Se utiliza la fuente del sistema para evitar descargas externas, mejorar el rendimiento y mantener una buena legibilidad.
- Fuente monoespaciada: ui-monospace para importes, conceptos y datos técnicos.
- Base móvil: 16 px, con razón 1,2.
- Base escritorio: 18 px, con razón 1,25.
- Se utiliza clamp() para adaptar los tamaños progresivamente al ancho de pantalla.
- Medida máxima de línea: 65ch para facilitar la lectura de los párrafos.

## 3. Espaciado y forma

- Escala de espaciado: 4, 8, 12, 16, 24, 32, 48 y 64 px.
- Se utilizan múltiplos de 4 para mantener la coherencia visual.
- Radio de controles: 8 px.
- Radio de tarjetas: 12 px.
- Píldoras: radio máximo.
- Se mantiene la escala de la plantilla para evitar valores arbitrarios.

## 4. Componentes (RA1 · CE f)

| Componente | Estados | Cómo se resuelve cada estado en CSS |
|---|---|---|
| Botón | Normal, hover, foco, desactivado y secundario | :hover, :focus-visible y :disabled |
| Turno | Disponible, seleccionado, ocupado y foco | :has(:checked), :has(:disabled) y :has(:focus-visible) |
| Contador de invitados | Normal, seleccionado y foco | :has(:checked) y :has(:focus-visible) |
| Aviso de pago | Normal | Borde de acento, fondo tenue y texto monoespaciado para el concepto |

Los componentes utilizan tokens semánticos y no dependen de JavaScript. Los estados se identifican mediante texto, bordes y otros indicadores, no solamente mediante colores.

## 5. Comparativa de tecnologías (RA1 · CE e · RA2 · CE i)

| Criterio | Figma | Penpot | Diseño en código |
|---|---|---|---|
| Coste / licencia | Propietario, con plan gratuito limitado | Código abierto y opción alojada | Sin coste de licencia |
| Traslado a código | Requiere trasladar valores y componentes | Permite inspeccionar y exportar diseños | Los estilos se crean directamente en código |
| Mantenimiento | Mediante variables y componentes | Mediante bibliotecas y componentes | Centralizado en SCSS y tokens |

| Criterio | Sass + CSS propio | CSS nativo sin preprocesador | Bootstrap / Tailwind |
|---|---|---|---|
| Tokens y temas | Mapas, funciones y variables | Custom Properties | Variables y utilidades |
| Peso del CSS final | Se compila únicamente el CSS necesario | No necesita compilación | Depende de los componentes y utilidades utilizados |
| Control de la cascada | Control mediante @layer | Control mediante @layer | Depende del framework y su configuración |

**Decisión y motivo:**

Se ha elegido trabajar con VS Code y Sass porque permite centralizar los valores del diseño, generar escalas automáticamente, comprobar contrastes durante la compilación y organizar los estilos mediante módulos.

Se descarta Figma y Penpot para este proyecto porque se ha decidido trabajar directamente sobre la guía de estilo en código.

Se descarta Bootstrap y Tailwind porque se busca mantener el control sobre los componentes, los tokens y la cascada CSS sin depender de un framework externo.
