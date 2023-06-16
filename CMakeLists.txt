cmake_minimum_required(VERSION 3.16.3)

project(cpp-lib-skeleton CXX)

#C++ Standard version required
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

#Build Shared lib by default
if(NOT DEFINED BUILD_SHARED_LIBS)
  set(BUILD_SHARED_LIBS ON)
endif()
if(NOT DEFINED CMAKE_POSITION_INDEPENDENT_CODE)
  set(CMAKE_POSITION_INDEPENDENT_CODE ${BUILD_SHARED_LIBS})
endif()

include_directories(include)
include_directories(src)

enable_testing()
add_subdirectory(tests)
