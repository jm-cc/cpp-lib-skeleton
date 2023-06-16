cmake_minimum_required(VERSION 3.16.3)

project(cpp-lib-skeleton CXX)

#C++ Standard version required
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include_directories(include)
include_directories(src)

enable_testing()
add_subdirectory(tests)
