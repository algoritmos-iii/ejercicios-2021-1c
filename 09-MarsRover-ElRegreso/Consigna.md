# Enunciado

El equipo de Mars Rover nos contrató nuevamente, ya que desean desarrollar distintos sistemas para hacer un seguimiento del robot en Marte. Para esta primera versión, nos han pedido las siguientes funcionalidades de seguimiento:

1. Tener un registro a archivos (un *log*) donde se vayan anotando los cambios de la posición y los cambios de hacia dónde apunta el Mars Rover. Se tiene que poder seguir sólo los cambios de posición, sólo los cambios de dirección o ambos (en el mismo *log*).

2. Tener una ventana (*window*) de información donde se muestre la posición actual y hacia dónde apunta el MarsRover actualmente, a partir de un movimiento del robot. De la misma forma que con el *log*, se debe poder visualizar sólo la posición actual, sólo los cambios de dirección o ambos (en la misma ventana).

Notar que, a diferencia del *log*, donde van quedando todos los cambios registrados, en la ventana sólo se muestra la situación actual en unos campos de texto.

Es necesario que la solución soporte que solo se esté usando el log, sólo la ventana o ambos.

Dado que se planea seguir extendiendo los sistemas de seguimiento, nuestra solución deberá cumplir con las siguientes restricciones:

1. Debe ser posible agregar otras maneras de hacer seguimiento, como mandar mensajes a un micro-servicio o grabar la información en una base de datos sin modificar el código existente.

2. Debe ser posible seguir los cambios de otros colaboradores futuros que el Mars Rover pueda tener. Por ejemplo, si se le agrega un colaborador con la temperatura del robot, se debe poder seguir los cambios de la misma de forma sencilla, con la menor cantidad de modificaciones posibles.

3. Al igual que con la ventana y el log, se debe poder utilizar múltiples formas de seguimiento al mismo tiempo, así como poder seguir cambios de múltiples colaboradores internos de forma independiente o en conjunto.

Implementar la solución haciendo TDD. Deben partir del código de la solución del Mars Rover anterior, ya sea el realizado por ustedes o a partir de la solución provista por la cátedra.

**Aclaración:** No es necesario que la ventana se dibuje realmente en pantalla, alcanza con tener un objeto que la represente. Respecto al archivo no es necesario que se persista de disco.
