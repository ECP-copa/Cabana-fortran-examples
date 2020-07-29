# project settings
cmake_minimum_required(VERSION 3.12)

project(CFE LANGUAGES CXX)

include(GNUInstallDirs)

# Use C++14
set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF) #...without compiler extensions like gnu++11

# Download and unpack googletest at configure time
include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/release-1.10.0.tar.gz
)
FetchContent_GetProperties(googletest)
if(NOT googletest_POPULATED)
  FetchContent_Populate(googletest)
  add_subdirectory(${googletest_SOURCE_DIR} ${googletest_BINARY_DIR})
endif()

# Prevent GoogleTest from overriding our compiler/linker options
# when building with Visual Studio
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)

enable_testing()

# find dependencies
find_package(Cabana REQUIRED)

enable_language(Fortran)
find_package(MPI REQUIRED COMPONENTS Fortran)
add_subdirectory(advanced_examples)
add_subdirectory(tutorial)
