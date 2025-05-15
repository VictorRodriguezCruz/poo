
# 📝 Ejercicios de Programación en Java (Nivel Progresivo)

---

## ✅ Ejercicio 1: Calculadora Básica
**Nivel:** Fácil  
**Tema:** Métodos y estructuras básicas

### Enunciado:
Crea una clase `Calculadora` que tenga métodos para sumar, restar, multiplicar y dividir dos números. Implementa una función `main` para probar cada operación.

### Ayuda (bloque base):
```java
public class Calculadora {
    public int sumar(int a, int b) {
        // ...
    }

    public int restar(int a, int b) {
        // ...
    }

    public int multiplicar(int a, int b) {
        // ...
    }

    public double dividir(int a, int b) {
        // ...
    }

    public static void main(String[] args) {
        // Pruebas aquí
    }
}
```

### Solución:
```java
public class Calculadora {
    public int sumar(int a, int b) {
        return a + b;
    }

    public int restar(int a, int b) {
        return a - b;
    }

    public int multiplicar(int a, int b) {
        return a * b;
    }

    public double dividir(int a, int b) {
        if (b == 0) {
            System.out.println("No se puede dividir entre 0.");
            return 0;
        }
        return (double) a / b;
    }

    public static void main(String[] args) {
        Calculadora calc = new Calculadora();
        System.out.println("Suma: " + calc.sumar(5, 3));
        System.out.println("Resta: " + calc.restar(5, 3));
        System.out.println("Multiplicación: " + calc.multiplicar(5, 3));
        System.out.println("División: " + calc.dividir(10, 2));
    }
}
```

---

## ✅ Ejercicio 2: Gestión de Estudiantes
**Nivel:** Básico  
**Tema:** Clases y objetos

### Enunciado:
Crea una clase `Estudiante` con nombre, edad y calificación. Implementa un método `mostrarInfo()` que imprima los datos. Luego crea 3 objetos y muestra su información.

### Ayuda (bloque base):
```java
public class Estudiante {
    // Atributos
    String nombre;
    int edad;
    double calificacion;

    // Constructor
    public Estudiante(String nombre, int edad, double calificacion) {
        // ...
    }

    public void mostrarInfo() {
        // ...
    }

    public static void main(String[] args) {
        // Crear estudiantes y mostrar info
    }
}
```

### Solución:
```java
public class Estudiante {
    String nombre;
    int edad;
    double calificacion;

    public Estudiante(String nombre, int edad, double calificacion) {
        this.nombre = nombre;
        this.edad = edad;
        this.calificacion = calificacion;
    }

    public void mostrarInfo() {
        System.out.println("Nombre: " + nombre + ", Edad: " + edad + ", Calificación: " + calificacion);
    }

    public static void main(String[] args) {
        Estudiante e1 = new Estudiante("Ana", 20, 8.5);
        Estudiante e2 = new Estudiante("Luis", 22, 9.0);
        Estudiante e3 = new Estudiante("María", 19, 7.8);

        e1.mostrarInfo();
        e2.mostrarInfo();
        e3.mostrarInfo();
    }
}
```

---

## ✅ Ejercicio 3: Herencia Vehículos
**Nivel:** Medio  
**Tema:** Herencia

### Enunciado:
Crea una clase base `Vehiculo` con el método `encender()`. Luego crea 2 clases hijas: `Auto` y `Motocicleta` que extienden de `Vehiculo` y sobrescriben el método `encender()`.

### Ayuda (bloque base):
```java
public class Vehiculo {
    public void encender() {
        // ...
    }
}

public class Auto extends Vehiculo {
    // ...
}

public class Motocicleta extends Vehiculo {
    // ...
}

public class Main {
    public static void main(String[] args) {
        // Crear objetos y probar métodos
    }
}
```

### Solución:
```java
public class Vehiculo {
    public void encender() {
        System.out.println("Vehículo encendido.");
    }
}

public class Auto extends Vehiculo {
    @Override
    public void encender() {
        System.out.println("Auto encendido.");
    }
}

public class Motocicleta extends Vehiculo {
    @Override
    public void encender() {
        System.out.println("Motocicleta encendida.");
    }
}

public class Main {
    public static void main(String[] args) {
        Vehiculo v1 = new Auto();
        Vehiculo v2 = new Motocicleta();

        v1.encender();
        v2.encender();
    }
}
```

---

## ✅ Ejercicio 4: Composición y Biblioteca
**Nivel:** Intermedio  
**Tema:** Composición de clases

### Enunciado:
Crea una clase `Libro` con título y autor, y una clase `Biblioteca` que tenga una lista de libros. Agrega un método para mostrar todos los libros.

### Ayuda (bloque base):
```java
import java.util.*;

class Libro {
    // ...
}

class Biblioteca {
    private List<Libro> libros;

    public Biblioteca() {
        // ...
    }

    public void agregarLibro(Libro libro) {
        // ...
    }

    public void mostrarLibros() {
        // ...
    }

    public static void main(String[] args) {
        // Crear libros y agregarlos
    }
}
```

### Solución:
```java
import java.util.*;

class Libro {
    String titulo;
    String autor;

    public Libro(String titulo, String autor) {
        this.titulo = titulo;
        this.autor = autor;
    }

    public void mostrar() {
        System.out.println(titulo + " de " + autor);
    }
}

class Biblioteca {
    private List<Libro> libros;

    public Biblioteca() {
        libros = new ArrayList<>();
    }

    public void agregarLibro(Libro libro) {
        libros.add(libro);
    }

    public void mostrarLibros() {
        for (Libro libro : libros) {
            libro.mostrar();
        }
    }

    public static void main(String[] args) {
        Biblioteca biblioteca = new Biblioteca();
        biblioteca.agregarLibro(new Libro("1984", "George Orwell"));
        biblioteca.agregarLibro(new Libro("El Principito", "Saint-Exupéry"));

        biblioteca.mostrarLibros();
    }
}
```
