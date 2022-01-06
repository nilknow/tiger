cmake_minimum_required(VERSION 3.20)
project(tiger C)

set(CMAKE_C_STANDARD 99)

include(CTest)
enable_testing()

include(CheckIncludeFile)
include(CheckIncludeFileCXX)
include(CheckIncludeFiles)
include(ExternalProject)

#include(thirdparty/tbb.cmake)

include_directories(${CMAKE_CURRENT_SOURCE_DIR}/include)

add_subdirectory(include)
add_subdirectory(thirdparty)
add_subdirectory(src)
add_subdirectory(test)

add_executable(tiger src/main.c test/unity_test.c)

add_library(matrix src/component/matrix.c)
target_include_directories(matrix
        PRIVATE
        ${PROJECT_SOURCE_DIR}/include)
