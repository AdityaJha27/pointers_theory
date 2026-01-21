
---

## 💻 `pointers.cpp`

```cpp
#include <iostream>
using namespace std;

// Function for function pointer demo
void func(float x)
{
    cout << "Function called with value: " << x << endl;
}

int main()
{
    // 1. Basic Pointer
    int b = 17;
    int c;
    int* a;

    a = &b;
    c = *a;

    cout << "Basic Pointer Demo" << endl;
    cout << "b = " << b << endl;
    cout << "Address stored in a = " << a << endl;
    cout << "Value pointed by a = " << *a << endl;
    cout << "c = " << c << endl;

    cout << "----------------------" << endl;

    // 2. Pointer to Pointer
    int** p2;
    p2 = &a;

    cout << "Pointer to Pointer Demo" << endl;
    cout << "Value using **p2 = " << **p2 << endl;

    cout << "----------------------" << endl;

    // 3. Array of Pointers
    int x = 5, y = 99, z = 17;
    int* arr[3];

    arr[0] = &x;
    arr[1] = &y;
    arr[2] = &z;

    cout << "Array of Pointers Demo" << endl;
    for (int i = 0; i < 3; i++)
    {
        cout << *arr[i] << endl;
    }

    cout << "----------------------" << endl;

    // 4. Pointer to Function
    void (*fp)(float);
    fp = func;

    cout << "Pointer to Function Demo" << endl;
    fp(1.2);

    cout << "----------------------" << endl;

    // 5. Pointer Arithmetic
    int a1[10] = {0, 1, 2, 3, 4, 5, 6, 7, 8, 9};
    int* c1 = &a1[0];

    cout << "Pointer Arithmetic Demo" << endl;

    c1 += 2;   // points to a1[2]
    cout << "After c1 += 2, value = " << *c1 << endl;

    c1++;      // points to a1[3]
    cout << "After c1++, value = " << *c1 << endl;

    int b1 = *c1++;
    cout << "b1 = " << b1 << endl;
    cout << "Now c1 points to value = " << *c1 << endl;

    *c1 = 3;
    cout << "Updated a1[4] = " << a1[4] << endl;

    (*c1)++;
    cout << "Incremented a1[4] = " << a1[4] << endl;

    return 0;
}
```
# swapping two numbers in pointers

```cpp
#include <iostream>
using namespace std;

// Function to swap two numbers using pointers
void swapNumbers(int* a, int* b)
{
    int temp = *a;
    *a = *b;
    *b = temp;
}

int main()
{
    int x, y;

    cout << "Enter first number: ";
    cin >> x;

    cout << "Enter second number: ";
    cin >> y;

    cout << "\nBefore Swapping:" << endl;
    cout << "x = " << x << endl;
    cout << "y = " << y << endl;

    // Call function with addresses
    swapNumbers(&x, &y);

    cout << "\nAfter Swapping (Using Pointers):" << endl;
    cout << "x = " << x << endl;
    cout << "y = " << y << endl;

    return 0;
}
```

# 1.memory_and_function_pointer

```cpp
#include <iostream>
using namespace std;

// Global variable
int globalVar = 10;

// Function to square a number
int square(int x)
{
    return x * x;
}

int main()
{
    // Local variable
    int localVar = 20;

    // Dynamic allocation
    int* dynamicVar = new int(30);

    cout << "=== Memory Regions ===" << endl;
    cout << "Global Variable Address: " << &globalVar << " (Global/Data Segment)" << endl;
    cout << "Local Variable Address: " << &localVar << " (Stack)" << endl;
    cout << "Dynamic Variable Address: " << dynamicVar << " (Heap)" << endl;

    cout << "\n=== Function Call ===" << endl;

    // Normal call
    cout << "Square (Normal Call): " << square(5) << endl;

    // Function pointer
    int (*fp)(int);
    fp = square;

    cout << "Square (Function Pointer Call): " << fp(5) << endl;

    delete dynamicVar;

    return 0;
}
```
# 2.value_address_pointer

```
#include <iostream>
using namespace std;

int main()
{
    int x = 50;
    int* p = &x;

    cout << "=== Variable & Pointer Info ===" << endl;
    cout << "Value of variable x: " << x << endl;
    cout << "Address of variable x: " << &x << endl;
    cout << "Value stored in pointer p (address of x): " << p << endl;
    cout << "Value pointed by pointer p: " << *p << endl;

    return 0;
}

```
# 3.dereference_copy

```
#include <iostream>
using namespace std;

int main()
{
    int a = 25;
    int b;
    int* p;

    p = &a;     // Pointer stores address of a
    b = *p;     // Copy value using dereferencing

    cout << "=== Dereferencing Copy Demo ===" << endl;
    cout << "Value of a: " << a << endl;
    cout << "Address of a: " << &a << endl;
    cout << "Pointer p stores address: " << p << endl;
    cout << "Value copied into b using *p: " << b << endl;

    return 0;
}


