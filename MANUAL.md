# Manual Esencial de C++ 

## Reglas INQUEBRANTABLES antes de empezar / TU CREDO 
1. **El punto y coma (;)**: Cada instruccion en C++ debe terminar con `;`. Es como el punto final en una oracion.
2. **Sensible a mayusculas**: `cout` no es lo mismo que `Cout`. C++ distingue entre mayusculas y minusculas.
3. **Las llaves {}**: Sirven para agrupar bloques de codigo (como el cuerpo de una funcion o un bucle).

## 1. La Estructura Basica (El Esqueleto)
Todo programa en C++ tiene una estructura minima. En 2026, la forma moderna de imprimir texto ya no es solo con `cout`, sino usando la libreria `<print>` (estandarizada en C++23), que es mas rapida y legible.

```cpp
// 1. Librerias: Herramientas que necesitamos
#include <print>   // Libreria moderna para imprimir en pantalla (C++23)
#include <string>  // Para usar texto (cadenas)

// 2. Espacio de nombres (Atajo para no escribir "std::" todo el tiempo)
using namespace std;

// 3. Funcion principal: Donde empieza a correr el programa
int main() {
    // 4. Instruccion: Imprimir en pantalla con salto de linea
    println("¡Hola, Mundo! Hablo C++ moderno"); 
    
    return 0; // 5. Termina el programa sin errores
}
```


## 2. Variables y Tipos de Datos
Las variables son "cajas" en la memoria para guardar informacion. En C++ debes decir que tipo de dato guardaras, aunque el C++ moderno introduce `auto` para deducir el tipo automaticamente.

```cpp
int edad = 25;           // Numeros enteros
double precio = 19.99;   // Numeros con decimales
char inicial = 'A';      // Un solo caracter (usa comillas simples '')
string nombre = "Ana";   // Texto o cadenas (usa comillas dobles "")
bool esMayor = true;     // Verdadero o Falso (true / false)

// 'auto' es el estandar moderno: el compilador deduce el tipo por ti
auto salario = 3500.50;  // El compilador sabe que es 'double'
auto equipo = "Real Madrid"; // El compilador sabe que es 'string'
```

## 3. Interaccion: Leer y Escribir
Hoy en dia usamos `print` y `println` para mostrar datos (usando llaves `{}` para insertar variables, similar a Python o C#), y `cin` para leer lo que escribe el usuario.

```cpp
int edad;
print("¿Cuantos anios tienes? "); // print no salta de linea
cin >> edad; // El programa se pausa y espera a que el usuario escriba y presione Enter

// println con formateo moderno usando {}
println("Tienes {} anios.", edad); 
```

## 4. Tomando Decisiones (if, else if, else)
Sirve para que el programa tome caminos distintos segun una condicion.

```cpp
int edad = 17;

if (edad >= 18) {
    println("Puedes entrar al concierto.");
} # Manual Esencial de C++ (Edicion 2026)
```

## Reglas de Oro antes de empezar

1. **El punto y coma (;)**: Cada instruccion en C++ debe terminar con `;`. Es como el punto final en una oracion.

2. **Sensible a mayusculas**: `cout` no es lo mismo que `Cout`. C++ distingue entre mayusculas y minusculas.

3. **Las llaves {}**: Sirven para agrupar bloques de codigo (como el cuerpo de una funcion o un bucle).



## 1. La Estructura Basica (El Esqueleto)

Todo programa en C++ tiene una estructura minima. En 2026, la forma moderna de imprimir texto ya no es solo con `cout`, sino usando la libreria `<print>` (estandarizada en C++23), que es mas rapida y legible.


```cpp

// 1. Librerias: Herramientas que necesitamos

#include <print>   // Libreria moderna para imprimir en pantalla (C++23)

#include <string>  // Para usar texto (cadenas)


// 2. Espacio de nombres (Atajo para no escribir "std::" todo el tiempo)

using namespace std;


// 3. Funcion principal: Donde empieza a correr el programa

int main() {

    // 4. Instruccion: Imprimir en pantalla con salto de linea

    println("¡Hola, Mundo! Hablo C++ moderno"); 

    

    return 0; // 5. Termina el programa sin errores

}

```
## 2. Variables y Tipos de Datos

Las variables son "cajas" en la memoria para guardar informacion. En C++ debes decir que tipo de dato guardaras, aunque el C++ moderno introduce `auto` para deducir el tipo automaticamente.


```cpp

int edad = 25;           // Numeros enteros

double precio = 19.99;   // Numeros con decimales

char inicial = 'A';      // Un solo caracter (usa comillas simples '')

string nombre = "Ana";   // Texto o cadenas (usa comillas dobles "")

bool esMayor = true;     // Verdadero o Falso (true / false)


// 'auto' es el estandar moderno: el compilador deduce el tipo por ti

auto salario = 3500.50;  // El compilador sabe que es 'double'

auto equipo = "Real Madrid"; // El compilador sabe que es 'string'

```


    


## 3. Interaccion: Leer y Escribir

Hoy en dia usamos `print` y `println` para mostrar datos (usando llaves `{}` para insertar variables, similar a Python o C#), y `cin` para leer lo que escribe el usuario.


```cpp

int edad;

print("¿Cuantos anios tienes? "); // print no salta de linea

cin >> edad; // El programa se pausa y espera a que el usuario escriba y presione Enter


// println con formateo moderno usando {}

println("Tienes {} anios.", edad); 

```

## 4. Tomando Decisiones (if, else if, else)

Sirve para que el programa tome caminos distintos segun una condicion.


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

Se usa cuando sabes cuantas veces quieres repetir algo. En 2026, el "bucle basado en rangos" es el estandar de oro para recorrer listas.


```cpp

// Bucle for clasico (Sintaxis: inicio; condicion; paso)

for (int i = 1; i <= 5; i++) { 

    println("Iteracion numero: {}", i);

}

```


### El bucle for basado en rangos (Moderno)

Se usa para recorrer colecciones de datos sin necesidad de usar indices numericos. Es mas seguro y limpio.

```cpp

// Se explicara a detalle en la seccion de Vectores

```


### El bucle while

Se usa cuando repites algo mientras se cumpla una condicion.

```cpp

int vidas = 3;

while (vidas > 0) {

    println("Te quedan {} vidas.", vidas);

    vidas--; // Restamos 1 vida

}

```

## 6. Funciones: Codigo Reutilizable

En lugar de copiar y pegar codigo, lo metes en una "funcion" y la llamas cuando la necesites.


```cpp

// Definicion de la funcion

// [tipo de retorno] [nombre] ([parametros])

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


    


## 7. Almacenamiento Multiple (Vectores)

En C++ moderno, usamos **Vectores** (`vector`) en lugar de los arreglos tradicionales, porque pueden cambiar de tamano dinamicamente y son mas seguros.

```cpp

#include <vector> // Necesitas esta libreria


int main() {

    // Crear un vector de enteros

    vector<int> numeros; 

    

    // Agregar elementos al final

    numeros.push_back(10);

    numeros.push_back(20);

    numeros.push_back(30);

    

    // Recorrer el vector con el "for basado en rangos" (Estandar actual en 2026)

    for (int numero : numeros) {

        print("{} ", numero); // Imprime: 10 20 30

    }

    println(""); // Salto de linea final

    

    return 0;

}

```


    


## 8. El "Sabor" C++: Referencias y Punteros

Esta es la parte que hace a C++ unico y extremadamente rapido. 

*   **Referencia (&)**: Es un "apodo" de una variable. Si cambias el apodo, cambia la original.

*   **Puntero (*)**: Es una variable que guarda la direccion de memoria de otra variable.


```cpp

int x = 10;


// REFERENCIA (El apodo)

int &refX = x; 

refX = 20; // Ahora 'x' tambien vale 20.


// PUNTERO (La direccion)

int *ptrX = &x; // Guardamos la direccion de memoria de 'x' (& significa "direccion de")

println("Valor: {}", *ptrX);  // Imprime 20 (* significa "ve el valor que hay en esa direccion")

```

*¿Para que sirven? Para pasar variables a funciones sin copiarlas (ahorrando memoria) y para crear estructuras de datos complejas.*


    


## 9. Introduccion a la Programacion Orientada a Objetos (Clases)

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

    

    // Metodo (Funcion dentro de una clase)

    void acelerar() {

        println("¡Vroom! El coche de {} acelera.", marca);

    }

};


int main() {

    Coche miAuto("Toyota", 2022); // Crear el objeto

    miAuto.acelerar();            // Usar su metodo

    return 0;

}

```


    


## ¿Como compilar y ejecutar tu codigo en 2026?

C++ no se ejecuta solo, necesita ser "traducido" a lenguaje maquina por un compilador (como `g++` o `clang++`). Para usar las caracteristicas modernas vistas en este manual (como `<print>`), debes indicarle al compilador que use el estandar C++23.


Si usas la terminal de Linux/Mac o WSL en Windows:

1. Guardas tu codigo en `main.cpp`.

2. Compilas con el estandar moderno: `g++ -std=c++23 main.cpp -o mi_programa`

3. Ejecutas: `./mi_programa` (En Windows seria `mi_programa.exe`).


*Tip: Si estas empezando, usa entornos gratuitos online que ya soportan C++23 como Compiler Explorer (godbolt.org) o OnlineGDB, o instala Visual Studio Code con la extension oficial de C/C++.*



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
Se usa cuando sabes cuantas veces quieres repetir algo. En 2026, el "bucle basado en rangos" es el estandar de oro para recorrer listas.

```cpp
// Bucle for clasico (Sintaxis: inicio; condicion; paso)
for (int i = 1; i <= 5; i++) { 
    println("Iteracion numero: {}", i);
}
```

### El bucle for basado en rangos (Moderno)
Se usa para recorrer colecciones de datos sin necesidad de usar indices numericos. Es mas seguro y limpio.
```cpp
// Se explicara a detalle en la seccion de Vectores
```

### El bucle while
Se usa cuando repites algo mientras se cumpla una condicion.
```cpp
int vidas = 3;
while (vidas > 0) {
    println("Te quedan {} vidas.", vidas);
    vidas--; // Restamos 1 vida
}
```

    

## 6. Funciones: Codigo Reutilizable
En lugar de copiar y pegar codigo, lo metes en una "funcion" y la llamas cuando la necesites.

```cpp
// Definicion de la funcion
// [tipo de retorno] [nombre] ([parametros])
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

    

## 7. Almacenamiento Multiple (Vectores)
En C++ moderno, usamos **Vectores** (`vector`) en lugar de los arreglos tradicionales, porque pueden cambiar de tamano dinamicamente y son mas seguros.

```cpp
#include <vector> // Necesitas esta libreria

int main() {
    // Crear un vector de enteros
    vector<int> numeros; 
    
    // Agregar elementos al final
    numeros.push_back(10);
    numeros.push_back(20);
    numeros.push_back(30);
    
    // Recorrer el vector con el "for basado en rangos" (Estandar actual en 2026)
    for (int numero : numeros) {
        print("{} ", numero); // Imprime: 10 20 30
    }
    println(""); // Salto de linea final
    
    return 0;
}
```

    

## 8. El "Sabor" C++: Referencias y Punteros
Esta es la parte que hace a C++ unico y extremadamente rapido. 
*   **Referencia (&)**: Es un "apodo" de una variable. Si cambias el apodo, cambia la original.
*   **Puntero (*)**: Es una variable que guarda la direccion de memoria de otra variable.

```cpp
int x = 10;

// REFERENCIA (El apodo)
int &refX = x; 
refX = 20; // Ahora 'x' tambien vale 20.

// PUNTERO (La direccion)
int *ptrX = &x; // Guardamos la direccion de memoria de 'x' (& significa "direccion de")
println("Valor: {}", *ptrX);  // Imprime 20 (* significa "ve el valor que hay en esa direccion")
```
*¿Para que sirven? Para pasar variables a funciones sin copiarlas (ahorrando memoria) y para crear estructuras de datos complejas.*

    

## 9. Introduccion a la Programacion Orientada a Objetos (Clases)
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
    
    // Metodo (Funcion dentro de una clase)
    void acelerar() {
        println("¡Vroom! El coche de {} acelera.", marca);
    }
};

int main() {
    Coche miAuto("Toyota", 2022); // Crear el objeto
    miAuto.acelerar();            // Usar su metodo
    return 0;
}
```

    

## ¿Como compilar y ejecutar tu codigo?
C++ no se ejecuta solo, necesita ser "traducido" a lenguaje maquina por un compilador (como `g++` o `clang++`). Para usar las caracteristicas modernas vistas en este manual (como `<print>`), debes indicarle al compilador que use el estandar C++23.

Si usas la terminal de Linux/Mac o WSL en Windows:
1. Guardas tu codigo en `main.cpp`.
2. Compilas con el estandar moderno: `g++ -std=c++23 main.cpp -o mi_programa`
3. Ejecutas: `./mi_programa` (En Windows seria `mi_programa.exe`).

*Tip: Si estas empezando, usa entornos gratuitos online que ya soportan C++23 como Compiler Explorer (godbolt.org) o OnlineGDB, o instala Visual Studio Code con la extension oficial de C/C++.*
