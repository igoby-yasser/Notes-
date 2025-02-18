# Unordered Set Operations in C++ (std::unordered_set)

## Introduction
This C++ program demonstrates various operations using `std::unordered_set<int>`, including insertion, retrieval, deletion, iteration, and checking for element existence. Unlike `std::set`, `std::unordered_set` **stores unique elements in an arbitrary order** and provides **average O(1) complexity** for most operations.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o unordered_set_operations unordered_set_operations.cpp
 ./unordered_set_operations
```

## 1. Insert Elements into an Unordered Set
```cpp
#include <iostream>
#include <unordered_set>

int main() {
    std::unordered_set<int> mySet;
    int n;
    
    std::cout << "Enter the number of elements: ";
    std::cin >> n;
    
    std::cout << "Enter " << n << " unique elements: ";
    for (int i = 0; i < n; ++i) {
        int value;
        std::cin >> value;
        mySet.insert(value);
    }
    return 0;
}
```

## 2. Check if an Element Exists in the Unordered Set
```cpp
    int value;
    std::cout << "Enter value to check: ";
    std::cin >> value;
    if (mySet.find(value) != mySet.end()) {
        std::cout << "Element exists in the unordered set." << std::endl;
    } else {
        std::cout << "Element not found!" << std::endl;
    }
```

## 3. Delete an Element from an Unordered Set
```cpp
    std::cout << "Enter value to delete: ";
    std::cin >> value;
    if (mySet.erase(value)) {
        std::cout << "Element deleted successfully." << std::endl;
    } else {
        std::cout << "Element not found in the unordered set." << std::endl;
    }
```

## 4. Iterate Over Elements in an Unordered Set
```cpp
    std::cout << "Unordered set elements: ";
    for (const auto &element : mySet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 5. Find the Size of the Unordered Set
```cpp
    std::cout << "The unordered set has " << mySet.size() << " elements." << std::endl;
```

## 6. Clear the Unordered Set (Remove All Elements)
```cpp
    mySet.clear();
    std::cout << "Unordered set cleared! Current size: " << mySet.size() << std::endl;
```

## 7. Example of Arbitrary Order
```cpp
    std::cout << "Inserting elements in order: 1, 5, 3, 2, 4\n";
    std::unordered_set<int> exampleSet = {1, 5, 3, 2, 4};
    std::cout << "Stored order: ";
    for (const auto &element : exampleSet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## Conclusion
`std::unordered_set` is an **unordered associative container** that ensures unique elements are stored in an **arbitrary order**. Unlike `std::set`, it provides **constant-time average complexity** for insertions, deletions, and lookups, making it ideal for **fast membership testing and hash-based operations**.

