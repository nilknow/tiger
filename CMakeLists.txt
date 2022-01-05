cmake_minimum_required(VERSION 3.20)
project(tiger C)

set(CMAKE_C_STANDARD 99)

add_executable(tiger main.c)
add_library(matrix component/matrix.c)
