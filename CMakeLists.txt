# project settings
cmake_minimum_required(VERSION 3.12)

project(AFE LANGUAGES CXX)

include(GNUInstallDirs)

# Use C++14
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF) #...without compiler extensions like gnu++11

# find dependencies
find_package(Cabana REQUIRED)

enable_language(Fortran)
find_package(MPI REQUIRED COMPONENTS Fortran)
add_subdirectory(advanced_examples)
