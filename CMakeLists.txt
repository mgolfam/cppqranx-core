# # CMakeLists.txt
# cmake_minimum_required(VERSION 3.12)
# project(qranxcore)

# set(CMAKE_CXX_STANDARD 14)

# include_directories(include)

# add_library(qranxcore src/*.cpp)

# # Add any other dependencies or settings

# # Example executable
# add_executable(example examples/main.cpp)
# target_link_libraries(example qranxcore)


# CMakeLists.txt for your library

cmake_minimum_required(VERSION 3.12)
project(qranxcore VERSION 1.0)

set(CMAKE_CXX_STANDARD 14)

# Add the library source files
add_library(qranxcore SHARED
    src/qranxcore.cpp
)

# Add any other dependencies or settings

# Set the library version
set_target_properties(qranxcore PROPERTIES VERSION ${PROJECT_VERSION})

# Install the library
install(TARGETS qranxcore
    LIBRARY DESTINATION lib
    PUBLIC_HEADER DESTINATION include/qranxcore
)
