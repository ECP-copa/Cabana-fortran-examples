# project settings
cmake_minimum_required(VERSION 3.12)

project(AFE LANGUAGES CXX)

include(GNUInstallDirs)

# Use C++14
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF) #...without compiler extensions like gnu++11

# find dependencies
find_package(Kokkos 3 REQUIRED)
find_package(Cabana REQUIRED)

enable_language(Fortran)
find_package(MPI REQUIRED COMPONENTS Fortran)
add_subdirectory(01_parallel_for)
add_subdirectory(02_push)
add_subdirectory(03_scatter)
add_subdirectory(04_unmanaged_aosoa)
add_subdirectory(Fortran_features)
