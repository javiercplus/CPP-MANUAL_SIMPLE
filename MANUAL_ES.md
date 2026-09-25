# Manual Esencial de C++ 

## Reglas de Oro antes de empezar / TU CREDO
1. **El punto y coma (;)**: Cada instrucción en C++ debe terminar con `;`. Es como el punto final en una oración.
2. **Sensible a mayúsculas**: `cout` no es lo mismo que `Cout`. C++ distingue entre mayúsculas y minúsculas.
3. **Las llaves {}**: Sirven para agrupar bloques de código (como el cuerpo de una función o un bucle).

   

## 1. La Estructura Básica (El Esqueleto)
Todo programa en C++ tiene una estructura mínima. En 2026, la forma moderna de imprimir texto ya no es solo con `cout`, sino usando la librería `<print>` (estandarizada en C++23), que es más rápida y legible.

```cpp
// 1. Librerías: Herramientas que necesitamos
#include <print>   // Librería moderna para imprimir en pantalla (C++23)
#include <string>  // Para usar texto (cadenas)

// 2. Espacio de nombres (Atajo para no escribir "std::" todo el tiempo)
using namespace std; 
// Nota: Aunque es excelente para aprender, en proyectos profesionales grandes se recomienda 
// usar "std::" explícitamente (ej. std::println) para evitar conflictos de nombres.

// 3. Función principal: Donde empieza a correr el programa
int main() {
    // 4. Instrucción: Imprimir en pantalla con salto de línea
    println("¡Hola, Mundo! Hablo C++ moderno"); 
    
    return 0; // 5. Termina el programa sin errores
}
```

   

## 2. Variables y Tipos de Datos
Las variables son "cajas" en la memoria para guardar información. En C++ debes decir qué tipo de dato guardarás, aunque el C++ moderno introduce `auto` para deducir el tipo automáticamente.

```cpp
int edad = 25;           // Números enteros
double precio = 19.99;   // Números con decimales
char inicial = 'A';      // Un solo carácter (usa comillas simples '')
string nombre = "Ana";   // Texto o cadenas (usa comillas dobles "")
bool esMayor = true;     // Verdadero o Falso (true / false)

// 'auto' es el estándar moderno: el compilador deduce el tipo por ti
auto salario = 3500.50;      // El compilador sabe que es 'double'
auto equipo = "Real Madrid"; // El compilador sabe que es 'string'
```

   

## 3. Interacción: Leer y Escribir
Hoy en día usamos `print` y `println` para mostrar datos (usando llaves `{}` para insertar variables, similar a Python o C#), y `cin` para leer lo que escribe el usuario.

```cpp
int edad;
print("¿Cuántos años tienes? "); // print no salta de línea
cin >> edad; // El programa se pausa y espera a que el usuario escriba y presione Enter

// println con formateo moderno usando {}
println("Tienes {} años.", edad); 
```

   

## 4. Tomando Decisiones (if, else if, else)
Permite que el programa tome caminos distintos según una condición.

```cpp
int edad = 17;

if (edad >= 18) {
    println("Puedes entrar al concierto.");
} 
else if (edad >= 15) {
    println("Puedes entrar, pero sin beber.");
} 
else {
    println("No puedes entrar.");
}
```
*Nota: Para comparar si dos cosas son iguales, se usa doble igual `==`. Un solo igual `=` es para asignar valores.*

   

## 5. Bucles: Repetir cosas (for y while)
### El bucle for
Se usa cuando sabes cuántas veces quieres repetir algo. En 2026, el "bucle basado en rangos" es el estándar de oro para recorrer listas.

```cpp
// Bucle for clásico (Sintaxis: inicio; condición; paso)
for (int i = 1; i <= 5; i++) { 
    println("Iteración número: {}", i);
}
```

### El bucle for basado en rangos (Moderno)
Se usa para recorrer colecciones de datos sin necesidad de usar índices numéricos. Es más seguro y limpio.
```cpp
// Ejemplo de bucle for basado en rangos moderno
vector<int> numeros = {10, 20, 30};
for (int numero : numeros) {
    println("{}", numero); // Imprime cada número limpiamente
}
```

### El bucle while
Se usa cuando repites algo mientras se cumpla una condición.
```cpp
int vidas = 3;
while (vidas > 0) {
    println("Te quedan {} vidas.", vidas);
    vidas--; // Restamos 1 vida
}
```

   

## 6. Funciones: Código Reutilizable
En lugar de copiar y pegar código, lo metes en una "función" y la llamas cuando la necesites.

```cpp
// Definición de la función
// [tipo de retorno] [nombre] ([parámetros])
int sumar(int a, int b) {
    return a + b; // Devuelve el resultado
}

void saludar(string nombre) { // 'void' significa que no devuelve nada
    println("¡Hola, {}!", nombre);
}

int main() {
    // Llamando a las funciones
    int resultado = sumar(5, 7);
    println("La suma es: {}", resultado);
    
    saludar("Carlos");
    
    return 0;
}
```

   

## 7. Almacenamiento Múltiple (Vectores)
En C++ moderno, usamos **Vectores** (`vector`) en lugar de los arreglos tradicionales, porque pueden cambiar de tamaño dinámicamente y son más seguros.

```cpp
#include <vector> // Necesitas esta librería
#include <print>  // para que println/print funcione

int main() {
    // Crear un vector de enteros
    vector<int> numeros; 
    
    // Agregar elementos al final
    numeros.push_back(10);
    numeros.push_back(20);
    numeros.push_back(30);
    
    // Recorrer el vector con el "for basado en rangos" (Estándar actual en 2026)
    for (int numero : numeros) {
        print("{} ", numero); // Imprime: 10 20 30 
    }
    println(""); // Salto de línea final
    
    return 0;
}
```

   

## 8. El "Sabor" C++: Referencias y Punteros
Esta es la parte que hace a C++ único y extremadamente rápido. 
*   **Referencia (&)**: Es un "apodo" de una variable. Si cambias el apodo, cambia la original.
*   **Puntero (*)**: Es una variable que guarda la dirección de memoria de otra variable.

```cpp
int x = 10;

// REFERENCIA (El apodo)
int &refX = x; 
refX = 20; // Ahora 'x' también vale 20.

// PUNTERO (La dirección)
int *ptrX = &x; // Guardamos la dirección de memoria de 'x' (& significa "dirección de")
println("Valor: {}", *ptrX);  // Imprime 20 (* significa "ve el valor que hay en esa dirección")
```
*¿Para qué sirven? Para pasar variables a funciones sin copiarlas (ahorrando memoria) y para crear estructuras de datos complejas.*

   

## 9. Introducción a la Programación Orientada a Objetos (Clases)
C++ permite crear tus propios tipos de datos usando **Clases** (plantillas para crear objetos).

```cpp
class Coche {
public: // Lo que es accesible desde fuera
    string marca;
    int anio;
    
    // Constructor (Se ejecuta al crear el objeto)
    Coche(string m, int a) {
        marca = m;
        anio = a;
    }
    
    // Método (Función dentro de una clase)
    void acelerar() {
        println("¡Vroom! El coche de {} acelera.", marca);
    }
};

int main() {
    Coche miAuto("Toyota", 2022); // Crear el objeto
    miAuto.acelerar();            // Usar su método
    return 0;
}
```

   

## ¿Cómo compilar y ejecutar tu código en 2026?
C++ no se ejecuta solo, necesita ser "traducido" a lenguaje máquina por un compilador (como `g++` o `clang++`). Para usar las características modernas vistas en este manual (como `<print>`), debes indicarle al compilador que use el estándar C++23.

Si usas la terminal de Linux/Mac o WSL en Windows:
1. Guardas tu código en `main.cpp`.
2. Compilas con el estándar moderno: `g++ -std=c++23 main.cpp -o mi_programa`
3. Ejecutas: `./mi_programa` (En Windows sería `mi_programa.exe`).

*Tip: Si estás empezando, usa entornos gratuitos online que ya soportan C++23 como Compiler Explorer (godbolt.org) o OnlineGDB, o instala Visual Studio Code con la extensión oficial de C/C++.*
