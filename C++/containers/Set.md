# Set Operations in C++ (std::set)

## Introduction
This C++ program demonstrates various operations using `std::set<int>`, including insertion, retrieval, deletion, iteration, and checking for element existence. Unlike `std::vector` and `std::deque`, `std::set` stores **sorted unique elements**, making it efficient for ordered data management.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o set_operations set_operations.cpp
 ./set_operations
```

## 1. Insert Elements into a Set
```cpp
#include <iostream>
#include <set>

int main() {
    std::set<int> mySet;
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

## 2. Check if an Element Exists in the Set
```cpp
    int value;
    std::cout << "Enter value to check: ";
    std::cin >> value;
    if (mySet.find(value) != mySet.end()) {
        std::cout << "Element exists in the set." << std::endl;
    } else {
        std::cout << "Element not found!" << std::endl;
    }
```

## 3. Delete an Element from a Set
```cpp
    std::cout << "Enter value to delete: ";
    std::cin >> value;
    if (mySet.erase(value)) {
        std::cout << "Element deleted successfully." << std::endl;
    } else {
        std::cout << "Element not found in the set." << std::endl;
    }
```

## 4. Iterate Over Elements in a Set
```cpp
    std::cout << "Set elements: ";
    for (const auto &element : mySet) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 5. Find the Size of the Set
```cpp
    std::cout << "The set has " << mySet.size() << " elements." << std::endl;
```

## 6. Clear the Set (Remove All Elements)
```cpp
    mySet.clear();
    std::cout << "Set cleared! Current size: " << mySet.size() << std::endl;
```

## 7. Retrieve the Smallest and Largest Elements
```cpp
    if (!mySet.empty()) {
        std::cout << "Smallest element: " << *mySet.begin() << std::endl;
        std::cout << "Largest element: " << *mySet.rbegin() << std::endl;
    }
```

## Conclusion
`std::set` is a **sorted associative container** that ensures unique elements are stored in **ascending order**. Unlike other containers, it provides efficient lookup operations via `.find()` and `.erase()`. It is ideal for scenarios where **ordered uniqueness** is required, such as maintaining a collection of distinct items efficiently.

