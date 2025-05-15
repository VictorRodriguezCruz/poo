
# Guía de Programación Orientada a Objetos (POO)

Esta guía está diseñada para introducirte a los fundamentos de la Programación Orientada a Objetos, presentando los temas en un orden pedagógico desde lo más básico hasta conceptos esenciales de nivel intermedio.

---

## Tabla de Contenido

1. Introducción a la POO
2. Clases y Objetos
3. Constructores
4. Modificadores de Acceso (`public`, `private`, `protected`)
5. Composición
6. Herencia
7. Clases Abstractas
8. Interfaces (Tema adicional complementario)
9. Polimorfismo (Tema adicional complementario)

Cada sección incluye una explicación, ejercicios prácticos con código base y soluciones.

---

## 1. Introducción a la POO

La POO es un paradigma de programación basado en el concepto de "objetos", que contienen datos y métodos. Es utilizada para organizar el código de manera modular, reutilizable y mantenible.

### Ejercicio 1.1
**Planteamiento:** Describe en tus propias palabras qué es un objeto y una clase.

**Respuesta:**
Una clase es una plantilla para crear objetos. Un objeto es una instancia de una clase, que tiene atributos (estado) y métodos (comportamiento).

---

## 2. Clases y Objetos

```java
class Persona {
    String nombre;
    int edad;

    void saludar() {
        System.out.println("Hola, mi nombre es " + nombre);
    }
}

public class Main {
    public static void main(String[] args) {
        Persona p = new Persona();
        p.nombre = "Ana";
        p.edad = 25;
        p.saludar();
    }
}
```

### Ejercicio 2.1
**Planteamiento:** Crear una clase `Coche` con los atributos `marca` y `modelo` y un método que imprima sus datos.

**Respuesta:**
```java
class Coche {
    String marca;
    String modelo;

    void mostrarDatos() {
        System.out.println("Marca: " + marca + ", Modelo: " + modelo);
    }
}
```

---

## 3. Constructores

Un constructor es un método especial que se ejecuta al crear un objeto.

```java
class Persona {
    String nombre;

    Persona(String nombre) {
        this.nombre = nombre;
    }

    void saludar() {
        System.out.println("Hola, soy " + nombre);
    }
}
```

### Ejercicio 3.1
**Planteamiento:** Crear un constructor para la clase `Coche` que inicialice sus atributos.

**Respuesta:**
```java
class Coche {
    String marca;
    String modelo;

    Coche(String marca, String modelo) {
        this.marca = marca;
        this.modelo = modelo;
    }
}
```

---

## 4. Modificadores de Acceso

Controlan la visibilidad de atributos y métodos:
- `public`: accesible desde cualquier parte.
- `private`: accesible solo dentro de la clase.
- `protected`: accesible dentro del mismo paquete o subclases.

### Ejercicio 4.1
**Planteamiento:** Modifica la clase `Persona` para que su atributo `nombre` sea privado y crea métodos `getNombre` y `setNombre`.

**Respuesta:**
```java
class Persona {
    private String nombre;

    public String getNombre() {
        return nombre;
    }

    public void setNombre(String nombre) {
        this.nombre = nombre;
    }
}
```

---

## 5. Composición

Es una relación "tiene un" entre clases.

```java
class Motor {
    String tipo;
}

class Coche {
    Motor motor;

    Coche() {
        motor = new Motor();
        motor.tipo = "V8";
    }
}
```

### Ejercicio 5.1
**Planteamiento:** Crear una clase `Direccion` y agregarla a la clase `Persona` como composición.

**Respuesta:**
```java
class Direccion {
    String ciudad;
    String calle;
}

class Persona {
    Direccion direccion = new Direccion();
}
```

---

## 6. Herencia

Permite crear una clase nueva que reutiliza miembros de otra clase.

```java
class Animal {
    void hacerSonido() {
        System.out.println("Sonido generico");
    }
}

class Perro extends Animal {
    void hacerSonido() {
        System.out.println("Guau");
    }
}
```

### Ejercicio 6.1
**Planteamiento:** Crear una clase `Gato` que herede de `Animal` y sobrescriba `hacerSonido`.

**Respuesta:**
```java
class Gato extends Animal {
    void hacerSonido() {
        System.out.println("Miau");
    }
}
```

---

## 7. Clases Abstractas

Una clase abstracta no se puede instanciar y puede tener métodos abstractos (sin implementación).

```java
abstract class Figura {
    abstract double area();
}

class Circulo extends Figura {
    double radio;

    Circulo(double radio) {
        this.radio = radio;
    }

    double area() {
        return Math.PI * radio * radio;
    }
}
```

### Ejercicio 7.1
**Planteamiento:** Crear una clase abstracta `Animal` con un método `hacerSonido`. Implementar una subclase `Vaca`.

**Respuesta:**
```java
abstract class Animal {
    abstract void hacerSonido();
}

class Vaca extends Animal {
    void hacerSonido() {
        System.out.println("Muuu");
    }
}
```

---

## 8. Interfaces (Complementario)

Una interfaz define métodos sin implementación que deben ser implementados por otras clases.

```java
interface Volador {
    void volar();
}

class Pajaro implements Volador {
    public void volar() {
        System.out.println("Estoy volando");
    }
}
```

---

## 9. Polimorfismo (Complementario)

Permite que una referencia de tipo padre apunte a objetos de clases hijas.

```java
Animal a = new Perro();
a.hacerSonido(); // Guau
```

---

Esta guía cubre los fundamentos esenciales de POO. Se recomienda practicar creando tus propias clases y jerarquías de objetos para afianzar los conceptos.
