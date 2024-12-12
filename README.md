# Undefined Behavior in C++ Vector Modification
This repository demonstrates a common but subtle error in C++ when modifying a `std::vector` through a raw pointer after using `push_back`.  The issue arises because `push_back` can cause the vector to reallocate its internal array, invalidating any existing pointers to its elements.

The `bug.cpp` file contains the erroneous code.  The `bugSolution.cpp` file demonstrates a safer alternative that avoids undefined behavior.

## How to reproduce
1. Clone this repository.
2. Compile and run `bug.cpp`.  Observe the potential for undefined behavior (e.g., a crash or unexpected results).
3. Compile and run `bugSolution.cpp`.  This version provides a safer, more reliable approach. 

## Lesson
Avoid using raw pointers to access `std::vector` elements if you are modifying the vector's size using methods like `push_back`, `insert`, or `erase`.  Use iterators or access elements by index instead to ensure correctness.