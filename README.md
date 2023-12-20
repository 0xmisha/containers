# s21_containers Library

This repository hosts the implementation of the `s21_containers.h` library, designed to provide a collection of container classes in C++.

## Introduction

In the realm of programming, containers play a vital role in storing and organizing sets of objects of the same type. This library offers a variety of container classes, each with unique characteristics and methods, catering to different organizational and functional needs.

### Container Types

- **Sequence Containers**: These include `list`, `vector`, `array`, `stack`, `queue`. They require linear time to access individual elements.
- **Associative Containers**: Such as `map`, `set`, `multiset`. These provide faster access to individual elements using keys.

### Features

- **Template Classes**: All container classes are templated, allowing them to handle various data types.
- **Standard Constructors**: Includes default, copy, move, and initialization list constructors.
- **Access Methods**: For element retrieval using indices or keys.
- **Capacity Checks**: Methods to check container fullness or emptiness.
- **Modification Methods**: Adding, removing, and clearing elements.
- **Iterators**: Providing pointer-like access to container elements.

### Iterators

Iterators in this library mimic C-style pointers and include operations like dereferencing (`*iter`), increment (`++iter`), decrement (`--iter`), and comparison (`iter1 == iter2`, `iter1 != iter2`).

## Development Specifications

- **Language**: C++ (C++17 Standard)
- **Compiler**: gcc
- **Code Style**: Google C++ Style Guide
- **Directory**: Source code in `src` folder
- **Namespace**: All classes under `s21` namespace
- **Testing**: Full coverage with GTest library
- **STL Implementation**: Followed STL logic

![UML](misc/STL_UML.png)

### Part 1: s21_containers.h Library

Implementation of main container classes: `list`, `map`, `queue`, `set`, `stack`, `vector`.

- **Structure**: Main header file `s21_containers.h` including separate headers for each container.
- **Makefile**: Provided for building and testing (`clean`, `test` targets).

### Part 2: s21_containersplus.h Library

Implementation of additional containers: `array`, `multiset`.

- **Structure**: Main header file `s21_containersplus.h` including separate headers for each container.
- **Makefile**: Provided for building and testing (`clean`, `test` targets).

### Part 3: `insert_many` Method

Enhancement of container classes with `insert_many` method to insert multiple elements.

| Modifiers      | Description                                      | Applicable Containers |
|----------------|--------------------------------------------------|-----------------------|
| `iterator insert_many(const_iterator pos, Args&&... args)` | Inserts elements before `pos` | List, Vector |
| `void insert_many_back(Args&&... args)` | Appends elements to the end | List, Vector, Queue |
| `void insert_many_front(Args&&... args)` | Appends elements to the top | List, Stack |
| `vector<std::pair<iterator,bool>> insert_many(Args&&... args)` | Inserts elements | Map, Set, Multiset |
