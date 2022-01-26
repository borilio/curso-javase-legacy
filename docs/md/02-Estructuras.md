

# Índice

[TOC]

------

# Tipos de instrucciones

Cada línea que escribimos en un programa es una instrucción. Estas instrucciones pueden ser:

- **Declaraciones:** Sirven definir (crear) una variable o funciones en un programa.
- **Primitivas**: Son acciones sobre los datos de los programas. A su vez puede ser:
  - **De asignación:** Cuando asignamos un valor a una variable.
  - **De Entrada o Salida (E/S):** Cuando mostramos una expresión por pantalla o leemos por teclado. La pantalla y el teclado son las E/S estándar, pero podría ser cualquier otro dispositivo.
- **Control:** Sirven para alterar y controlar el orden de ejecución de un programa. En general, todos los programas se ejecutan secuencialmente línea a línea, y gracias a estas estructuras el flujo del programa puede depender de ciertas condiciones que nosotros elijamos.



Ejemplo de instrucción de declaración:

```java
String curso = "Java";
```

Ejemplo de instrucción de asignación:

```java
curso = curso + "SE por Salva Márquez";
```

Ejemplo de instrucciones de E/S:

```java
System.out.print("Introduzca su edad: ");	//Instrucción de SALIDA
int edad = scanner.nextInt();				//Instrucción de ENTRADA
```

Ejemplo de instrucción de control:

```java
//Si la expresión es verdadera, se ejecuta la primera sentencia
//en caso contrario, la segunda.
if (gremlinBueno == true && hora > 23) {
    System.out.println("No es hora de comer"); 
} else {
    System.out.println("Puedes comer un poquito");
}
```

Veamos a fondo las distintas instrucciones de control en Java en el siguiente apartado.

# Instrucciones de control

Todas las instrucciones anteriormente vistas, son secuenciales. Se ejecutan una tras otra y en ningún momento se varia el flujo del programa. Pero la programación estructurada permite el uso de condiciones y de iteraciones.

Estas instrucciones permiten que ciertas líneas de código se ejecuten o no, dependiendo de una condición (**instrucciones condicionales**), e incluso repetidamente hasta o mientras se cumpla una condición (**instrucciones repetitivas**). En definitiva son instrucciones que permiten variar el flujo normal del programa.

## Expresiones lógicas

Para variar el flujo, usaremos condiciones que decidirán si se modifica o no el flujo, saltando bloques de código o repitiéndolos. Una condición es una **expresión lógica** o **booleana**. 

Una expresión lógica es una operación donde el resultado siempre será un valor lógico, verdadero o falso. Nunca dará cualquier otro resultado. En java los valores serán `true` o `false`. 

Suelen ser comparaciones entre datos. Por ejemplo, `5 > 8`, da como resultado `false`. `"Hola" == "Ola"` da como resultado `false`. De la misma forma que `1+(1*3)/8` es una expresión matemática, y su resultado será un número, en una expresión lógica su resultado deberá ser `true` o `false`.

Para “operar” en una expresión lógica en java, usaremos los siguientes operadores en Java:

- `>` Mayor que
- `<` Menor que
- `>=` Mayor o igual que
- `<=` Menor o igual que
- `==` Igual que
- `!=` Distinto que
- `&&` Y (and)
- `||` O (or)
- `!` No (not)

## Instrucción condicional simple

{{if}}

## Instrucción condicional doble

{{if-else}}

## Instrucción condicional compuesta

{{switch}}

## Instrucción repetitiva While

{{while}}

## Instrucción repetitiva Do… While

{{do-while}}

## Instrucción repetitiva For

{{for}}

## Instrucciones anidadas

{{ex}}

















