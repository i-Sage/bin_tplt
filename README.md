# C++ Binary Project Template

This repo is a starting point for creating C++ projects that produce executable binaries. It includes a basic directory structure and a CMake-based build system and using vcpkg as a package manager.

## Getting Started

### Prerequisites

- CMake (version 3.29 or higher).
- C++ compiler supporting >= C++17 standard.
- vcpkg package manager.

### Building and Usage

Run the following command: cmake -B build -S . -DCMAKE_TOOLCHAIN_FILE=%VCPKG_ROOT%\scripts\buildsystems\vcpkg.cmake, but substitute %VCPKG_ROOT% with your vcpkg installation path.

Run the following command to build the project cmake --build build
