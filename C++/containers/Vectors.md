# Vector Operations in C++ (std::vector)

## Introduction
This C++ program demonstrates various operations using `std::vector<int>`, including insertion, retrieval, updating, deletion, iteration, and clearing elements. Unlike `std::array`, `std::vector` supports **dynamic resizing**, making it more flexible for handling variable-sized data sets.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o vector_operations vector_operations.cpp
 ./vector_operations
```

## 1. Insert Elements into a Vector
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<int> vec;
    int n;
    
    std::cout << "Enter the number of elements: ";
    std::cin >> n;
    
    std::cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n; ++i) {
        int value;
        std::cin >> value;
        vec.push_back(value);
    }
    return 0;
}
```

## 2. Access Elements from a Vector
```cpp
    int index;
    std::cout << "Enter the index to access: ";
    std::cin >> index;
    if (index >= 0 && index < vec.size()) {
        std::cout << "Element at index " << index << " is: " << vec.at(index) << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## Explanation of `.at()`
The `.at(index)` function in `std::vector` provides **bounds-checked** access to elements. If the index is out of range, it throws a `std::out_of_range` exception instead of causing undefined behavior, making it safer than direct indexing (`vec[index]`).

## 3. Update an Element in a Vector
```cpp
    int index, newValue;
    std::cout << "Enter index and new value: ";
    std::cin >> index >> newValue;
    if (index >= 0 && index < vec.size()) {
        vec.at(index) = newValue;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 4. Delete an Element from a Vector
```cpp
    std::cout << "Enter index to delete: ";
    std::cin >> index;
    if (index >= 0 && index < vec.size()) {
        vec.erase(vec.begin() + index);
        std::cout << "Element deleted successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 5. Iterate Over Elements in a Vector
```cpp
    std::cout << "Vector elements: ";
    for (const auto &element : vec) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 6. Find the Size of the Vector
```cpp
    std::cout << "The vector has " << vec.size() << " elements." << std::endl;
```

## 7. Clear the Vector (Remove All Elements)
```cpp
    vec.clear();
    std::cout << "Vector cleared! Current size: " << vec.size() << std::endl;
```

## 8. Two-Dimensional Vectors
```cpp
#include <iostream>
#include <vector>

int main() {
    std::vector<std::vector<int>> matrix(3, std::vector<int>(4, 0)); // 3x4 matrix initialized with 0
    
    std::cout << "Enter elements for a 3x4 matrix: \n";
    for (int i = 0; i < 3; ++i) {
        for (int j = 0; j < 4; ++j) {
            std::cin >> matrix[i][j];
        }
    }
    
    std::cout << "Matrix elements:\n";
    for (const auto &row : matrix) {
        for (const auto &element : row) {
            std::cout << element << " ";
        }
        std::cout << std::endl;
    }
    return 0;
}
```

## Additional Operations
### Append Elements to the Vector
```cpp
    int value;
    std::cout << "Enter a value to add: ";
    std::cin >> value;
    vec.push_back(value);
    std::cout << "Element added." << std::endl;
```

### Remove Last Element from the Vector
```cpp
    if (!vec.empty()) {
        vec.pop_back();
        std::cout << "Last element removed." << std::endl;
    } else {
        std::cout << "Vector is already empty!" << std::endl;
    }
```

### Get First and Last Elements
```cpp
    if (!vec.empty()) {
        std::cout << "First element: " << vec.front() << std::endl;
        std::cout << "Last element: " << vec.back() << std::endl;
    }
```

### Get Underlying Data Pointer
```cpp
    int* dataPtr = vec.data();
    std::cout << "Pointer to first element: " << *dataPtr << std::endl;
```

## Conclusion
`std::vector` is a **dynamic array** that provides flexibility, safety, and additional operations compared to `std::array` or traditional C-style arrays. With built-in bounds checking via `.at()`, dynamic resizing using `.push_back()` and `.erase()`, and iterator support, it is the preferred choice for handling dynamic collections in C++.

