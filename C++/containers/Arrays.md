# Array Operations in C++

## Introduction
This C++ program demonstrates various operations using arrays, including insertion, retrieval, updating, deletion, iteration, and clearing elements.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o array_operations array_operations.cpp
 ./array_operations
```

## 1. Insert Elements
```cpp
#include <iostream>

int main() {
    int n;
    std::cout << "Enter the number of elements: ";
    std::cin >> n;
    int arr[n];
    
    std::cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n; ++i) {
        std::cin >> arr[i];
    }
    return 0;
}
```

## 2. Access Elements
```cpp
    int index;
    std::cout << "Enter the index to access: ";
    std::cin >> index;
    if (index >= 0 && index < n) {
        std::cout << "Element at index " << index << " is: " << arr[index] << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 3. Update an Element
```cpp
    int index, newValue;
    std::cout << "Enter index and new value: ";
    std::cin >> index >> newValue;
    if (index >= 0 && index < n) {
        arr[index] = newValue;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 4. Delete an Element (Shifting Approach)
```cpp
    int index;
    std::cout << "Enter index to delete: ";
    std::cin >> index;
    if (index >= 0 && index < n) {
        for (int i = index; i < n - 1; ++i) {
            arr[i] = arr[i + 1];
        }
        --n;
        std::cout << "Element deleted successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 5. Iterate Over Elements
```cpp
    std::cout << "Array elements: ";
    for (int i = 0; i < n; ++i) {
        std::cout << arr[i] << " ";
    }
    std::cout << std::endl;
```

## 6. Find the Size of the Array
```cpp
    std::cout << "Current size of array: " << n << std::endl;
```

## 7. Clear the Array
```cpp
    n = 0;
    std::cout << "Array cleared! Current size: " << n << std::endl;
```
