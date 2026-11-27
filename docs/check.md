## A1   Color y tipografía
1. El uso de clamp no da un tamaño exacto ya que es un tamaño relativo, nos indica que el tamaño calculado no va a ser nunca menor al segundo establecido o mayor que el indicado, realmente no he encontrado ningún recurso donde se diga cuantos px equivale, ya que seguramente px y rem no esten diseñados para la misma funcionalidad

2. --color-acento es el nombre de un color que hemos declarado anteriormente en el token de estilos.css, en mi caso son tonos marrones, uno oscuro y otro claro, para que e use en el modo oscuro y en el modo claro, en cambio cuando lo usamos junto a color: tenemos que añadir var (--color-acento) teniendo como resultado color: var(--color-acento); para que se utilice el color ya predefinido y no ir cada vez que queramos el color en otro componente, buscando uno por uno el color, así evitarnos que sean distintos colores por muy ligero que sea y respetando la paleta de colores

## A2 Tecnologias del Diseño
1. Dependiendo del tipo de pagina que quiera diseñar, por ejemplo para otra de este estilo igual vuelvo a utilizar este sistema ya que tengo conocimientos sobre el, en cambio, para una pagina tipo landing, que es como si fuera un escaparate (muy correcta para marketing) y tiene poco donde interactuar, haría uso de ASTRO, ya que se divide por secciones y a mi forma de verlo es muy comodo y la curva de aprendizaje es muy facil.

## A3 Preprocesadores
1. --color-acento pasa por _elementos.scss Y estilos.css y llega a los siguientes componentes
_aviso.scss
_boton.scss
_guia.scss
_invitados.scss
_turno.scss

2. `@use` se usa para importar todos los elementos creados en x carpeta que se le asigne donde se especifique en el archivo donde se usa. Por ejemplo en `_boton.scss` se usa el `use "../abstracts" as *` refiriendose a que se usen todos los recursos de abstracts en todo el fichero. En cambio `@forward` se usa para exponer variables y funciones de otros archivos usados en la misma carpeta.

3. Falso como una catedrál hay que compilarlo para que funcione correctamente con el comando npm

## A4 Navegacion de la pagina nueva
1. Usaría un botón de flujo al final de cada pagina en turnos y mis turnos, ya que son las que se usan para interactuar con las pistas, ya que normas es indicativa y aviso, privacidad son más de caracter legislativo

2. El usuario una vez ha enviado la incidencia le sale un mensaje de estado (fallo al enviar la incidencia / incidencia enviada) y se le redirige a la pagina de inicio  y si no se envia un boton de cancelar

3. En hoja de examen se encuentra el mapa

4. Considero que no debe ir en el menú ya que es algo de caracter ocasional y está en las paginas donde se les hace uso.

