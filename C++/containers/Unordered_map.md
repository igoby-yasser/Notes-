# Unordered Map Operations in C++

## Introduction
This C++ program demonstrates various operations using `std::unordered_map`, including insertion, retrieval, updating, deletion, iteration, and clearing elements.

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o unordered_map_operations unordered_map_operations.cpp
 ./unordered_map_operations
```

## 1. Insert Elements
```cpp
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    std::unordered_map<std::string, int> myMap;
    int n;
    std::cout << "Enter the number of elements: ";
    std::cin >> n;
    for (int i = 0; i < n; ++i) {
        std::string key;
        int value;
        std::cout << "Enter key and value: ";
        std::cin >> key >> value;
        myMap[key] = value;
    }
    return 0;
}
```

## 2. Access Elements
```cpp
    std::cout << "Enter a key to access its value: ";
    std::string key;
    std::cin >> key;
    if (myMap.find(key) != myMap.end()) {
        std::cout << "Value: " << myMap[key] << std::endl;
    } else {
        std::cout << "Key not found!" << std::endl;
    }
```

## 3. Check If a Key Exists
```cpp
    std::cout << "Enter a key to check existence: ";
    std::cin >> key;
    if (myMap.find(key) != myMap.end()) {
        std::cout << "The key exists in the map." << std::endl;
    } else {
        std::cout << "The key does not exist." << std::endl;
    }
```

## 4. Update an Existing Value
```cpp
    std::cout << "Enter key and new value: ";
    std::cin >> key >> n;
    if (myMap.find(key) != myMap.end()) {
        myMap[key] = n;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Key does not exist." << std::endl;
    }
```

## 5. Erase an Element
```cpp
    std::cout << "Enter a key to erase: ";
    std::cin >> key;
    if (myMap.erase(key)) {
        std::cout << "Key erased successfully." << std::endl;
    } else {
        std::cout << "Key not found." << std::endl;
    }
```

## 6. Iterate Over Elements
```cpp
    for (const auto &pair : myMap) {
        std::cout << pair.first << " : " << pair.second << std::endl;
    }
```

## 7. Check Size of the Map
```cpp
    std::cout << "Current size: " << myMap.size() << std::endl;
```

## 8. Clear All Elements
```cpp
    myMap.clear();
    std::cout << "Map cleared! Current size: " << myMap.size() << std::endl;
```

## 9. Main difference between Map and unordered map
```cpp
    unorderedMap[3] = "Three";
    unorderedMap[1] = "One";
    unorderedMap[2] = "Two";
    ----> The output is not sorted by key.
```

