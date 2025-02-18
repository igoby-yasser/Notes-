# Static Array Operations in C++ (std::array)

## Introduction
This C++ program demonstrates various operations using `std::array<int, N>`, including insertion, retrieval, updating, deletion, iteration, and clearing elements. Unlike traditional C-style arrays, `std::array` provides additional safety features like bounds checking with `.at()`, size retrieval, and iterator support.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o static_array_operations static_array_operations.cpp
 ./static_array_operations
```

## 1. Insert Elements into a Static Array
```cpp
#include <iostream>
#include <array>

int main() {
    const int size = 5;
    std::array<int, size> arr;
    
    std::cout << "Enter " << size << " elements: ";
    for (int i = 0; i < size; ++i) {
        std::cin >> arr[i];
    }
    return 0;
}
```

## 2. Access Elements from a Static Array
```cpp
    int index;
    std::cout << "Enter the index to access: ";
    std::cin >> index;
    if (index >= 0 && index < size) {
        std::cout << "Element at index " << index << " is: " << arr.at(index) << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## Explanation of `.at()`
The `.at(index)` function in `std::array` provides **bounds-checked** access to elements. If the index is out of range, it throws a `std::out_of_range` exception instead of causing undefined behavior, making it safer than direct indexing (`arr[index]`).

## 3. Update an Element in a Static Array
```cpp
    int index, newValue;
    std::cout << "Enter index and new value: ";
    std::cin >> index >> newValue;
    if (index >= 0 && index < size) {
        arr.at(index) = newValue;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 4. Delete an Element (Replace with Zero or Default Value)
```cpp
    std::cout << "Enter index to delete: ";
    std::cin >> index;
    if (index >= 0 && index < size) {
        arr.at(index) = 0; // Setting to zero as deletion is not direct in arrays
        std::cout << "Element deleted (set to zero)." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 5. Iterate Over Elements in a Static Array
```cpp
    std::cout << "Array elements: ";
    for (const auto &element : arr) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 6. Find the Size of the Static Array
```cpp
    std::cout << "The array has " << arr.size() << " elements." << std::endl;
```

## 7. Clear the Static Array (Set All Elements to Zero)
```cpp
    arr.fill(0);
    std::cout << "Array cleared! All elements set to zero." << std::endl;
```

## Additional Operations
### Get First and Last Elements
```cpp
    std::cout << "First element: " << arr.front() << std::endl;
    std::cout << "Last element: " << arr.back() << std::endl;
```

### Get Underlying Data Pointer
```cpp
    int* dataPtr = arr.data();
    std::cout << "Pointer to first element: " << *dataPtr << std::endl;
```

## Conclusion
`std::array` provides a safer and more functional alternative to C-style arrays by incorporating features like `.at()` for bounds checking, `.size()` for retrieving the number of elements, and `.fill()` for bulk updates. It is a fixed-size container that integrates seamlessly with the STL while maintaining the performance characteristics of C-style arrays.

