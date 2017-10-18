# cmake version
cmake_minimum_required(VERSION 2.8.10 FATAL_ERROR)

# define project name and language
project(MyProject CXX)

# MPI
find_package(MPI REQUIRED)
include_directories(${MPI_INCLUDE_PATH})
set(INCLUDE ${MPI_INCLUDE_PATH})

# define executable names
set(EXE MyProgram)

# define directories
set(SRC ${CMAKE_SOURCE_DIR}/src)

add_subdirectory(${SRC})
