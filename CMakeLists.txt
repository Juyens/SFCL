cmake_minimum_required(VERSION 3.20)
project(SFCL VERSION 0.1.0 LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(sfcl
        src/Window.cpp
        include/SFCL/Window.hpp)
add_library(sfcl::sfcl ALIAS sfcl)

target_include_directories(sfcl PUBLIC include)

add_executable(sfcl_example
        examples/main.cpp)
target_link_libraries(sfcl_example PRIVATE sfcl)