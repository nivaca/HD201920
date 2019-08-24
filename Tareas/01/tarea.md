# Herramientas digitales 2019-20
## Módulo: Texto digital
## Profesor Nicolás Vaughan (n.vaughan@uniandes.edu.co)

## Tarea No. 1: Markdown, RegEx y Pandoc

**Fecha de entrega:** viernes 30 de agosto de 2019, 4:00 pm

**Modo de entrega:** A mi correo envíen los dos archivos resultantes (el `.md` y el `.html`), con su apellido como nombre de archivo (e.g. `vaughan.md`, `vaughan.html`). El asunto del correo debe ser `Tarea No. 1`.

## Descripción corta
Deben procesar un archivo de texto plano, transformándolo con RegEx en uno de formato Markdown, y finalmente en uno de formato HTML, con ayuda de Pandoc.

## Descripción detallada

Usando el motor RegEx del editor de texto Atom, deben procesar el texto *La gente cursi: Novela de Costumbres Ridículas*, de Ramón Ortega y Frías
(disponible aquí: https://www.gutenberg.org/cache/epub/47768/pg47768.txt). Deben guardarlo como un documento de Markdown (con extensión `.md`).
(Eliminen las primeras 62 líneas, y la parte en inglés al final, que no hacen parte del texto.)


Procesen el texto con RegEx (buscando y reemplazando) para hacer lo siguiente:

1. Unan las líneas (eliminando los saltos de línea) que componen los párrafos, teniendo cuidado de no eliminar los párrafos también. (Como vimos en la sesión virtual.)
2. Los dobles guiones (--) conviértanlos en rayas (—). (Las rayas son los guiones largos que se usan, entre otras, para indicar diálogos. Cf. http://bit.ly/2MB0i19)
3. Los comillones («») conviértanlos en comillas dobles: (“”).
4. Eliminen los espacios en blanco dobles (triples, etc.) entre palabras y al principio de las líneas.
5. Reemplacen por asteriscos los guiones bajos que encierran algunas palabras (por ejemplo, de: `_cursi_` a: `*cursi*`).
6. Dejen los títulos de capítulos en *una sola línea*.
Por ejemplo, de:
```
CAPÍTULO I

La mujer casamentera.
```

pasen a:

```
CAPÍTULO I: La mujer casamentera.
```

Noten los dos puntos (:) luego del número romano. Para este paso deberán usar grupos de captura (*capture groups*) de RegEx, para capturar todo el texto desde "Capítulo" hasta el final de la línea. (Usen paréntesis para eso en el campo de búsqueda, y luego `$1` en el campo de reemplazar. Vean http://bit.ly/322jFDI)

7. Usando la sintaxis de Markdown, marquen los capítulos como encabezados (*headers*) de nivel 2, como vimos en clase. (No se olviden del Epílogo y el Índice al final.) Antes de cada capítulo pongan una línea de separación (`***` en Markdown).

8. Marquen el título del libro y el autor como encabezados de nivel 1.

9. Limpien el índice del final del documento y denle formato de lista no numerada en Markdown.

10. Pongan los siguientes nombres en negrita: "Robustiana", "Juanito", "Alfredo", "Bonacha", "Pascual", "Paquita" y "Adela".
(Esto se puede hacer esto en un solo paso, usando un grupo de captura alternado `(Alfredo|Bonacha|...)`.)

11. Finalmente, conviertan el documento a HTML.

***

A continuación encontrarán el texto resultante en PDF para que vean cómo debe quedar. (Lo hice abriendo en Chrome el HTML y luego convirtiéndolo a PDF.)