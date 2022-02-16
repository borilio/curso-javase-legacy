# Índice

[TOC]

------

# Introducción

Una colección en Java, es un objeto que agrupa múltiples elementos dentro de otro objeto. Las colecciones implementan diferentes comportamientos de almacenamiento, recuperación y navegación.

Se utilizan para organizar los datos y acceder a ellos de una forma rápida (ya que están en memoria), pudiendo insertar, actualizar, obtener y eliminar elementos. 

Son similares a los arrays, pero estos tienen las siguientes limitaciones:

- Los arrays tienen un tamaño fijo. No pueden cambiar de forma dinámica su tamaño. Ni aumentan, ni disminuyen.
- No proveen distintas formas de almacenar o acceder a los datos.
- No poseen formas automáticas de ordenación. 

Para superar dichas limitaciones, utilizamos las Colecciones. 

Las colecciones nos ofrecen los siguientes beneficios:

- Menos esfuerzo al manejarlas: Ya poseen una estructura de datos y algoritmos para agrupar, ordenar, insertar, borrar, y buscar sus elementos.
- Fácil de aprender: Gastamos menos tiempo para comprender la lógica para agrupar y ordenar una colección, que si lo hiciéramos manualmente de otra forma.
- Mejoran la calidad del código: Usamos clases que ya están muy probadas y refinadas en su funcionamiento y eficiencia.
- Reusabilidad: Una colección se puede usar incluso para API diferentes formando un lenguaje común para pasar objetos.

# Vista general

El esquema de colecciones de Java es muy complejo, y veremos tan solo algunas implementaciones de las interfaces más comúnmente usadas.

![Esquema-Colecciones](img/04/02.png)

- Interfaz **`List`**: Su implementación más usada es la clase **`ArrayList`**.
- Interfaz **`Set`**: Su implementación más usada es la clase **`TreeSet`**.
- Interfaz **`Map`**: Su implementación más usada es la clase **`HashMap`**.

# Métodos comunes

Todas las colecciones poseen unas operaciones básicas comunes. Después cada colección posee sus propios métodos particulares. Las operaciones básicas para todas las colecciones son las siguientes:

- Añadir un objeto a la colección. Se realiza con el método <kbd>add</kbd>.
- Borrar un objeto de la colección. Se realiza con el método <kbd>remove</kbd>. 
- Obtener el tamaño de la colección. Se realiza con el método <kbd>size</kbd>.
- Comprobar si un objeto se encuentra en la colección. Se realiza con el método <kbd>contains</kbd>.
- Comprobar su una colección está vacía. Se realiza con el método <kbd>isEmpty</kbd>.
- Obtener un elemento de la colección. Se realiza con el método <kbd>get</kbd>.
- Eliminar todos los elementos de la colección. Se realiza con el método <kbd>clear</kbd>.

Cada colección sobrescribirá sus propios métodos, adaptándolos a sus necesidades, pudiendo existir diferencias entre una colección y otra, por lo que siempre consultaremos la documentación de los mismos, para comprobar que hace cada método, sus valores devueltos, posibles excepciones lanzadas, etc.

## Bucle FOR EACH

Es un bucle especial, que no lo vimos en el momento de las estructuras repetitivas, y ahora es el momento. Está especialmente diseñado para recorrer colecciones y arrays, y con el que no necesitamos manejar ningún índice, tal y como hacemos con el `for` tradicional. Su sintaxis es la siguiente:

```java
for (TipoDato objeto : nombreColección ) {
    instrucciones...
}
```

Veamos un ejemplo concreto para mostrar todos los elementos de un array de Strings.

```java
String[] nombres = {"Tony", "Bruce", "Peter", "Natasha", "Steve", "Clint"};
for (String nombre : nombres) {
    System.out.println(nombre)
}
```

El bucle `for…each` anterior imprimiría en cada vuelta, los nombres del array en orden secuencial. No tendríamos que manejar un índice ni incrementarlo para poder acceder a los elementos por su posición, lo cual nos puede ahorrar muchos errores de acceso a índices erróneos. 

Si necesitamos recorrer el array o colección de una forma que no sea estrictamente secuencial, por ejemplo, recorrerla al revés, o de dos en dos, como necesitamos acceder a posiciones concretas del array, no podríamos usar el `for…each` y necesitaríamos un `for` tradicional y para poder manejar el índice.

# List

Son colecciones basadas en índices, como los arrays (de ahí su nombre), que permiten duplicados y se almacenan en base a una posición. 

La implementación más común de la Interfaz **List**, es la clase **[ArrayList](https://docs.oracle.com/javase/8/docs/api/java/util/ArrayList.html)**. También existe **[LinkedList](https://docs.oracle.com/javase/8/docs/api/java/util/LinkedList.html)** la cual ofrece mejor rendimiento en determinadas circunstancias.

Su sintaxis es la siguiente:

```java
List<Objeto> nombreColección = new ArrayList<Objeto>();
```

Creamos un nuevo objeto del tipo `ArrayList` y debemos parametrizar el tipo de dato que albergará la colección. 

> **Nota:** Si no parametrizamos la colección con <>, estaremos creando una colección de Object, lo cual nos permitiría crear una colección de cualquier tipo de objeto todos mezclados. Se recomienda encarecidamente siempre crear una colección de un tipo de objeto determinado.

Veamos un ejemplo para crear un ArrayList de Strings.

```java
List<String> lista = new ArrayList<String>();
```

> 🤓 Se considera una buena práctica para el uso de colecciones, el declarar la variable del tipo de la interfaz (`List`) que es más genérico, e inicializarla con el nombre de la especialización (`ArrayList`). De esta forma, en la misma variable `lista`, podremos guardar un ArrayList, o cualquier otro objeto que implemente la interfaz List, como un LinkedList. **Haremos lo mismo para todas las demás colecciones.**

Así estamos creando el objeto `lista`, que será un `ArrayList`, que contendrá `String`. Inicialmente se crea un ArrayList vacío, y deberemos añadirle elementos con el método <kbd>add</kbd>. Como le hemos indicado que será una colección de `String`, el método `add` sólo admitirá objetos de esa clase.

```java
// Añadimos objetos a la lista
lista.add("Tony");
lista.add("Bruce");
lista.add("Clint");
lista.add("Steve");
lista.add("Natasha");
lista.add("Peter");
```

Cada vez que insertamos un elemento, este se posiciona al final de la lista.

Para acceder a los elementos de la lista, usaremos el método <kbd>get</kbd>, el cual recibe un entero que representa el índice (posición) del elemento dentro del ArrayList. Sus índices empiezan en 0, igual que los arrays.

```java
System.out.println(lista.get(2)); // Clint
```

La colección List, posee todos los métodos comunes que hemos descrito con anterioridad, como `contains`, `isEmpty`, `clear`, `remove`, etc. Lo mejor siempre para comprobar los métodos de una colección será crear el objeto y escribir su nombre  y un punto para que el IDE nos muestre la lista de todos los métodos disponibles, así como la documentación de como usarlos.

**Características**

- Son de propósito general y muy versátiles en todos los aspectos
- Están basadas en índices
- Admiten duplicados
- No tienen un orden natural por defecto
- Acceso directo por posición
- Son muy parecidos a los arrays, y por eso familiares para todos los programadores.

# Set





**Características**

- ba
- ba
- ba
- 



# Map





**Características**

- ba
- ba
- ba
- 

# ¿Cual colección usar?

Entre tantas colecciones, es posible que a veces no tengamos claro cual usar que se adapte mejor a las necesidades, tanto en funcionamiento como en eficiencia. El siguiente cuadro te ayudará a escoger la más adecuada. 

Algunas clases o interfaces no se han visto en el curso. Pero si se ajustan a lo que necesitas, y conociendo las bases de las colecciones, verás que no es nada difícil aprender a manejar una nueva, ya que seguro que comparten muchos métodos y comportamientos con otra que si conoces.

![Decisión-Colecciones](img/04/01.png)





