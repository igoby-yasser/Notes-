# List Operations in C++ (std::list)

## Introduction
This C++ program demonstrates various operations using `std::list<int>`, including insertion, retrieval, updating, deletion, iteration, and clearing elements. Unlike `std::vector`, `std::list` is implemented as a **doubly-linked list**, making it efficient for frequent insertions and deletions at any position.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o list_operations list_operations.cpp
 ./list_operations
```

## 1. Insert Elements into a List
```cpp
#include <iostream>
#include <list>

int main() {
    std::list<int> myList;
    int n;
    
    std::cout << "Enter the number of elements: ";
    std::cin >> n;
    
    std::cout << "Enter " << n << " elements: ";
    for (int i = 0; i < n; ++i) {
        int value;
        std::cin >> value;
        myList.push_back(value);
    }
    return 0;
}
```

## 2. Access Elements in a List
```cpp
    std::cout << "List elements: ";
    for (const auto &element : myList) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 3. Update an Element in a List
```cpp
    int oldValue, newValue;
    std::cout << "Enter the value to replace and the new value: ";
    std::cin >> oldValue >> newValue;
    for (auto &element : myList) {
        if (element == oldValue) {
            element = newValue;
            break;
        }
    }
    std::cout << "Updated successfully." << std::endl;
```

## 4. Delete an Element from a List
```cpp
    int value;
    std::cout << "Enter value to delete: ";
    std::cin >> value;
    myList.remove(value);
    std::cout << "Element deleted successfully." << std::endl;
```

## 5. Iterate Over Elements in a List
```cpp
    std::cout << "List elements: ";
    for (const auto &element : myList) {
        std::cout << element << " ";
    }
    std::cout << std::endl;
```

## 6. Find the Size of the List
```cpp
    std::cout << "The list has " << myList.size() << " elements." << std::endl;
```

## 7. Clear the List (Remove All Elements)
```cpp
    myList.clear();
    std::cout << "List cleared! Current size: " << myList.size() << std::endl;
```

## 8. Insert Elements at the Front
```cpp
    int value;
    std::cout << "Enter a value to insert at the front: ";
    std::cin >> value;
    myList.push_front(value);
    std::cout << "Element added at the front." << std::endl;
```

## 9. Insert Elements at a Specific Position
```cpp
    int pos, value;
    std::cout << "Enter position (0-based index) and value to insert: ";
    std::cin >> pos >> value;
    auto it = myList.begin();
    std::advance(it, pos);
    myList.insert(it, value);
    std::cout << "Element inserted successfully." << std::endl;
```

## 10. Reverse the List
```cpp
    myList.reverse();
    std::cout << "List reversed." << std::endl;
```

## Conclusion
`std::list` is a **doubly-linked list** that provides efficient insertions and deletions at any position. Unlike `std::vector`, it does not provide direct access by index but is more efficient for frequent modifications. Operations like `.push_front()`, `.remove()`, `.insert()`, and `.reverse()` make it a powerful tool for managing dynamic collections.

