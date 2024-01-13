cmake_minimum_required(VERSION 3.12)

project(LinearAlgebraLibrary)

set(CMAKE_CXX_STANDARD 11)

include_directories(include)

# Add source files
file(GLOB SOURCES "src/*.cpp")

# Create a library
add_library(LinearAlgebra ${SOURCES})

# Add executable for tests
add_executable(tests tests/MatrixTest.cpp tests/ComplexTest.cpp)
target_link_libraries(tests LinearAlgebra)

# Add executable for examples
add_executable(example examples/main.cpp)
target_link_libraries(example LinearAlgebra)
