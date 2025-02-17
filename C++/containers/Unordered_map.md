# Unordered Map Operations in C++

## Introduction
This C++ program demonstrates various operations using `std::unordered_map`, including insertion, retrieval, updating, deletion, iteration, and clearing elements.

## Features
The program allows users to perform the following operations:
1. **Insert Elements**: Add key-value pairs to the unordered map.
2. **Access Elements**: Retrieve the value associated with a given key.
3. **Check Key Existence**: Verify if a key exists in the map.
4. **Update an Existing Value**: Modify the value of an existing key.
5. **Erase an Element**: Remove a key-value pair from the map.
6. **Iterate Over Elements**: Display all key-value pairs stored in the map.
7. **Check Map Size**: Print the current size of the map.
8. **Clear All Elements**: Remove all elements from the map.

## Code
```cpp
#include <iostream>
#include <unordered_map>
#include <string>

int main() {
    std::unordered_map<std::string, int> myMap;
    int n;

    std::cout << "====================================" << std::endl;
    std::cout << "      UNORDERED MAP OPERATIONS      " << std::endl;
    std::cout << "====================================" << std::endl;

    // 1. INSERT ELEMENTS (User Input)
    std::cout << "\n[1] INSERT ELEMENTS" << std::endl;
    std::cout << "Enter the number of elements: ";
    std::cin >> n;

    for (int i = 0; i < n; ++i) {
        std::string key;
        int value;
        std::cout << "Enter key and value: ";
        std::cin >> key >> value;
        myMap[key] = value;
    }

    // 2. ACCESS ELEMENTS
    std::cout << "\n[2] ACCESS ELEMENTS" << std::endl;
    std::cout << "Enter a key to access its value: ";
    std::string key;
    std::cin >> key;
    if (myMap.find(key) != myMap.end()) {
        std::cout << "Value: " << myMap[key] << std::endl;
    } else {
        std::cout << "Key not found!" << std::endl;
    }

    // 3. CHECK IF A KEY EXISTS
    std::cout << "\n[3] CHECK IF A KEY EXISTS" << std::endl;
    std::cout << "Enter a key to check existence: ";
    std::cin >> key;
    if (myMap.find(key) != myMap.end()) {
        std::cout << "The key exists in the map." << std::endl;
    } else {
        std::cout << "The key does not exist." << std::endl;
    }

    // 4. UPDATE AN EXISTING VALUE
    std::cout << "\n[4] UPDATE AN EXISTING VALUE" << std::endl;
    std::cout << "Enter key and new value: ";
    std::cin >> key >> n;
    if (myMap.find(key) != myMap.end()) {
        myMap[key] = n;
        std::cout << "Updated successfully." << std::endl;
    } else {
        std::cout << "Key does not exist." << std::endl;
    }

    // 5. ERASE AN ELEMENT
    std::cout << "\n[5] ERASE AN ELEMENT" << std::endl;
    std::cout << "Enter a key to erase: ";
    std::cin >> key;
    if (myMap.erase(key)) {
        std::cout << "Key erased successfully." << std::endl;
    } else {
        std::cout << "Key not found." << std::endl;
    }

    // 6. ITERATE OVER ELEMENTS
    std::cout << "\n[6] ITERATE OVER ELEMENTS" << std::endl;
    for (const auto &pair : myMap) {
        std::cout << pair.first << " : " << pair.second << std::endl;
    }

    // 7. CHECK SIZE OF THE MAP
    std::cout << "\n[7] CHECK SIZE OF THE MAP" << std::endl;
    std::cout << "Current size: " << myMap.size() << std::endl;

    // 8. CLEAR ALL ELEMENTS
    std::cout << "\n[8] CLEAR ALL ELEMENTS" << std::endl;
    myMap.clear();
    std::cout << "Map cleared! Current size: " << myMap.size() << std::endl;

    return 0;
}
```

## Compilation and Execution
To compile and run the program, use the following commands in a terminal:
```sh
 g++ -o unordered_map_operations unordered_map_operations.cpp
 ./unordered_map_operations
```

## Usage Example
```
====================================
      UNORDERED MAP OPERATIONS      
====================================

[1] INSERT ELEMENTS
Enter the number of elements: 3
Enter key and value: apple 10
Enter key and value: banana 20
Enter key and value: cherry 30

[2] ACCESS ELEMENTS
Enter a key to access its value: banana
Value: 20

[3] CHECK IF A KEY EXISTS
Enter a key to check existence: orange
The key does not exist.

[4] UPDATE AN EXISTING VALUE
Enter key and new value: apple 50
Updated successfully.

[5] ERASE AN ELEMENT
Enter a key to erase: banana
Key erased successfully.

[6] ITERATE OVER ELEMENTS
cherry : 30
apple : 50

[7] CHECK SIZE OF THE MAP
Current size: 2

[8] CLEAR ALL ELEMENTS
Map cleared! Current size: 0
```

## Conclusion
This program serves as a basic demonstration of `std::unordered_map` and its functionalities in C++. It is useful for managing key-value pairs efficiently while providing fast lookups, insertions, and deletions.

## Author
Your Name : Baouzil Yasser

## License
This project is licensed under the MIT License - see the LICENSE file for details.

