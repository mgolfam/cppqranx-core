# CMakeLists.txt for your project

# cmake_minimum_required(VERSION 3.12)
# project(example-release)

# set(CMAKE_CXX_STANDARD 14)

# # Add the library directory
# # libqranxcore
# add_subdirectory(qranxcore)

# # Link against the library
# target_link_libraries(example-release libqranxcore)

# CMakeLists.txt for your project

cmake_minimum_required(VERSION 3.12)
project(exampletest)

set(CMAKE_CXX_STANDARD 14)

# Add the directory containing the shared library header
include_directories(libs/qranxcore)
# add_subdirectory(libs/qranxcore)


# Add the shared library
add_library(qranxcore SHARED IMPORTED)
# set_target_properties(qranxcore PROPERTIES IMPORTED_LOCATION libs/qranxcore/libqranxcore.so)

# Add your project's source files
add_executable(exampletest
    src/main.cpp
)

# Link against the shared library
target_link_libraries(exampletest PRIVATE ${CMAKE_SOURCE_DIR}/libs/qranxcore/libqranxcore.so)
