# Deque Operations in C++ (std::deque)

## Introduction
This C++ program demonstrates various operations using `std::deque<int>`, including insertion, retrieval, updating, deletion, iteration, and clearing elements. Unlike `std::vector`, `std::deque` supports **fast insertions and deletions** at both the front and the back, making it efficient for use cases requiring frequent modifications at both ends.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o deque_operations deque_operations.cpp
 ./deque_operations
```

## 1. Insert Elements into a Deque
```cpp
#include <iostream>
#include <deque>

int main() {
    std::deque<int> myDeque;
    int n;
    
    std::cout << "Enter the number of elements: ";
    std::cin >> n;
    
    std::cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n; ++i) {
        int value;
        std::cin >> value;
        myDeque.push_back(value);
    }
    return 0;
}
```

## 2. Access Elements in a Deque
```cpp
    int index;
    std::cout << "Enter the index to access: ";
    std::cin >> index;
    if (index >= 0 && index < myDeque.size()) {
        std::cout << "Element at index " << index << " is: " << myDeque.at(index) << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 3. Update an Element in a Deque
```cpp
    int index, newValue;
    std::cout << "Enter index and new value: ";
    std::cin >> index >> newValue;
    if (index >= 0 && index < myDeque.size()) {
        myDeque.at(index) = newValue;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 4. Delete an Element from a Deque
```cpp
    std::cout << "Enter index to delete: ";
    std::cin >> index;
    if (index >= 0 && index < myDeque.size()) {
        myDeque.erase(myDeque.begin() + index);
        std::cout << "Element deleted successfully." << std::endl;
    } else {
        std::cout << "Index out of bounds!" << std::endl;
    }
```

## 5. Iterate Over Elements in a Deque
```cpp
    std::cout << "Deque elements: ";
    for (const auto &element : myDeque) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 6. Find the Size of the Deque
```cpp
    std::cout << "The deque has " << myDeque.size() << " elements." << std::endl;
```

## 7. Clear the Deque (Remove All Elements)
```cpp
    myDeque.clear();
    std::cout << "Deque cleared! Current size: " << myDeque.size() << std::endl;
```

## 8. Insert Elements at the Front
```cpp
    int value;
    std::cout << "Enter a value to insert at the front: ";
    std::cin >> value;
    myDeque.push_front(value);
    std::cout << "Element added at the front." << std::endl;
```

## 9. Insert Elements at a Specific Position
```cpp
    int pos, value;
    std::cout << "Enter position (0-based index) and value to insert: ";
    std::cin >> pos >> value;
    auto it = myDeque.begin();
    std::advance(it, pos);
    myDeque.insert(it, value);
    std::cout << "Element inserted successfully." << std::endl;
```

## 10. Remove Elements from the Front or Back
```cpp
    if (!myDeque.empty()) {
        myDeque.pop_front();
        std::cout << "Front element removed." << std::endl;
    }
    if (!myDeque.empty()) {
        myDeque.pop_back();
        std::cout << "Back element removed." << std::endl;
    }
```

## Conclusion
`std::deque` is a **dynamic array with fast insertions and deletions** at both the front and back. Unlike `std::vector`, it allows efficient modifications at both ends while providing random access to elements. Operations like `.push_front()`, `.push_back()`, `.pop_front()`, and `.pop_back()` make it an excellent choice for managing dynamic collections efficiently.

