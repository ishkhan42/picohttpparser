cmake_minimum_required(VERSION 3.14 FATAL_ERROR)
project(picohttpparser LANGUAGES CXX)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED YES)
set(CMAKE_CXX_EXTENSIONS NO)

# Make Release by default
if(NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE Release)
endif()

add_library(picohttpparser picohttpparser.hpp picohttpparser.cpp)

add_executable(picohttpparser_bench bench.cpp)
target_link_libraries(picohttpparser_bench picohttpparser)
