# Multi-Dimensional Array Operations in C++

## Introduction
This C++ program demonstrates various operations using multi-dimensional arrays, including insertion, retrieval, updating, deletion, iteration, and clearing elements.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o multi_array_operations multi_array_operations.cpp
 ./multi_array_operations
```

## 1. Insert Elements into a 2D Array
```cpp
#include <iostream>

int main() {
    int rows, cols;
    std::cout << "Enter number of rows and columns: ";
    std::cin >> rows >> cols;
    int arr[rows][cols];
    
    std::cout << "Enter elements for " << rows << "x" << cols << " matrix: \n";
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            std::cin >> arr[i][j];
        }
    }
    return 0;
}
```

## 2. Access Elements from a 2D Array
```cpp
    int row, col;
    std::cout << "Enter row and column index to access: ";
    std::cin >> row >> col;
    if (row >= 0 && row < rows && col >= 0 && col < cols) {
        std::cout << "Element at (" << row << ", " << col << ") is: " << arr[row][col] << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 3. Update an Element in a 2D Array
```cpp
    int row, col, newValue;
    std::cout << "Enter row, column and new value: ";
    std::cin >> row >> col >> newValue;
    if (row >= 0 && row < rows && col >= 0 && col < cols) {
        arr[row][col] = newValue;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 4. Delete an Element (Replace with Zero or Default Value)
```cpp
    std::cout << "Enter row and column index to delete: ";
    std::cin >> row >> col;
    if (row >= 0 && row < rows && col >= 0 && col < cols) {
        arr[row][col] = 0; // Setting to zero as deletion is not direct in arrays
        std::cout << "Element deleted (set to zero)." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 5. Iterate Over Elements in a 2D Array
```cpp
    std::cout << "Matrix elements:\n";
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            std::cout << arr[i][j] << " ";
        }
        std::cout << std::endl;
    }
```

## 6. Find the Size of the 2D Array
```cpp
    std::cout << "The matrix has " << rows << " rows and " << cols << " columns." << std::endl;
```

## 7. Clear the 2D Array (Set All Elements to Zero)
```cpp
    for (int i = 0; i < rows; ++i) {
        for (int j = 0; j < cols; ++j) {
            arr[i][j] = 0;
        }
    }
    std::cout << "Array cleared! All elements set to zero." << std::endl;
```

