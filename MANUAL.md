# Essential C++ Manual 

## Golden Rules before starting / YOUR CREED
1. **The semicolon (;)**: Every statement in C++ must end with `;`. It's like the period at the end of a sentence.
2. **Case-sensitive**: `cout` is not the same as `Cout`. C++ distinguishes between uppercase and lowercase.
3. **Braces {}**: They are used to group blocks of code (like the body of a function or a loop).

  

## 1. The Basic Structure (The Skeleton)
Every C++ program has a minimal structure. In 2026, the modern way to print text is no longer just with `cout`, but by using the `<print>` library (standardized in C++23), which is faster and more readable.

```cpp
// 1. Libraries: Tools we need
#include <print>   // Modern library for printing to screen (C++23)
#include <string>  // To use text (strings)

// 2. Namespace (Shortcut to avoid writing "std::" all the time)
using namespace std; 
// Note: While great for learning, in large professional projects it is recommended 
// to use "std::" explicitly (e.g., std::println) to avoid naming conflicts.

// 3. Main function: Where the program starts running
int main() {
    // 4. Statement: Print to screen with line break
    println("Hello, World! I speak modern C++");
    
    return 0; // 5. Ends the program without errors
}
```

  

## 2. Variables and Data Types
Variables are "boxes" in memory to store information. In C++ you must say what type of data you will store, although modern C++ introduces `auto` to deduce the type automatically.

```cpp
int age = 25;           // Integers
double price = 19.99;   // Decimal numbers
char initial = 'A';     // A single character (uses single quotes '')
string name = "Ana";    // Text or strings (uses double quotes "")
bool isAdult = true;    // True or False (true / false)

// 'auto' is the modern standard: the compiler deduces the type for you
auto salary = 3500.50;      // The compiler knows it is 'double'
auto team = "Real Madrid";  // The compiler knows it is 'string'
```

  

## 3. Interaction: Read and Write
Nowadays we use `print` and `println` to display data (using braces `{}` to insert variables, similar to Python or C#), and `cin` to read what the user types.

```cpp
int age;
print("How old are you? "); // print does not skip a line
cin >> age; // The program pauses and waits for the user to type and press Enter

// println with modern formatting using {}
println("You are {} years old.", age);
```

  

## 4. Making Decisions (if, else if, else)
It allows the program to take different paths depending on a condition.

```cpp
int age = 17;

if (age >= 18) {
    println("You can enter the concert.");
} 
else if (age >= 15) {
    println("You can enter, but without drinking.");
} 
else {
    println("You cannot enter.");
}
```
*Note: To compare if two things are equal, you use double equals `==`. A single equals `=` is for assigning values.*

  

## 5. Loops: Repeating things (for and while)
### The for loop
It is used when you know how many times you want to repeat something. In 2026, the "range-based loop" is the gold standard for traversing lists.

```cpp
// Classic for loop (Syntax: start; condition; step)
for (int i = 1; i <= 5; i++) { 
    println("Iteration number: {}", i);
}
```

### The range-based for loop (Modern)
It is used to traverse data collections without needing to use numeric indices. It is safer and cleaner.
```cpp
// Example of modern range-based for loop
vector<int> numbers = {10, 20, 30};
for (int number : numbers) {
    println("{}", number); // Prints each number cleanly
}
```

### The while loop
It is used when you repeat something while a condition is met.
```cpp
int lives = 3;
while (lives > 0) {
    println("You have {} lives left.", lives);
    lives--; // We subtract 1 life
}
```

  

## 6. Functions: Reusable Code
Instead of copying and pasting code, you put it in a "function" and call it when you need it.

```cpp
// Function definition
// [return type] [name] ([parameters])
int add(int a, int b) {
    return a + b; // Returns the result
}

void greet(string name) { // 'void' means it returns nothing
    println("Hello, {}!", name);
}

int main() {
    // Calling the functions
    int result = add(5, 7);
    println("The sum is: {}", result);
    
    greet("Carlos");
    
    return 0;
}
```

  

## 7. Multiple Storage (Vectors)
In modern C++, we use **Vectors** (`vector`) instead of traditional arrays, because they can change size dynamically and are safer.

```cpp
#include <vector> // You need this library
#include <print>  // Added for println/print

int main() {
    // Create a vector of integers
    vector<int> numbers; 
    
    // Add elements at the end
    numbers.push_back(10);
    numbers.push_back(20);
    numbers.push_back(30);
    
    // Traverse the vector with the "range-based for" (Current standard in 2026)
    for (int number : numbers) {
        print("{} ", number); // Prints: 10 20 30 
    }
    println(""); // Final line break
    
    return 0;
}
```

  

## 8. The "Flavor" of C++: References and Pointers
This is the part that makes C++ unique and extremely fast. 
*   **Reference (&)**: It is a "nickname" for a variable. If you change the nickname, the original changes.
*   **Pointer (*)**: It is a variable that stores the memory address of another variable.

```cpp
int x = 10;

// REFERENCE (The nickname)
int &refX = x; 
refX = 20; // Now 'x' is also 20.

// POINTER (The address)
int *ptrX = &x; // We store the memory address of 'x' (& means "address of")
println("Value: {}", *ptrX);  // Prints 20 (* means "see the value at that address")
```
*Why use them? To pass variables to functions without copying them (saving memory) and to create complex data structures.*

  

## 9. Introduction to Object-Oriented Programming (Classes)
C++ allows you to create your own data types using **Classes** (templates for creating objects).

```cpp
class Car {
public: // What is accessible from outside
    string brand;
    int year;
    
    // Constructor (Runs when the object is created)
    Car(string m, int a) {
        brand = m;
        year = a;
    }
    
    // Method (Function inside a class)
    void accelerate() {
        println("Vroom! The {} car accelerates.", brand);
    }
};

int main() {
    Car myCar("Toyota", 2022); // Create the object
    myCar.accelerate();        // Use its method
    return 0;
}
```

  

## How to compile and run your code in 2026?
C++ does not run by itself; it needs to be "translated" to machine language by a compiler (like `g++` or `clang++`). To use the modern features seen in this manual (like `<print>`), you must tell the compiler to use the C++23 standard.

If you use the Linux/Mac terminal or WSL on Windows:
1. Save your code in `main.cpp`.
2. Compile with the modern standard: `g++ -std=c++23 main.cpp -o my_program`
3. Run: `./my_program` (On Windows it would be `my_program.exe`).

*Tip: If you are just starting, use free online environments that already support C++23 like Compiler Explorer (godbolt.org) or OnlineGDB, or install Visual Studio Code with the official C/C++ extension.*
