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
add_subdirectory(src)

enable_testing()
add_subdirectory(tests)

#Documentation
option(ENABLE_DOC "Allow to build documentation" OFF)
if (ENABLE_DOC)
  find_package(Doxygen REQUIRED)
  set(DOXYGEN_OUTPUT_DIRECTORY "${CMAKE_CURRENT_BINARY_DIR}/doxygen/")
  set(DOXYGEN_EXTRACT_ALL "YES")
  set(DOXYGEN_EXTRACT_PRIVATE "YES")
  set(DOXYGEN_RECURSIVE "YES")
  set(DOXYGEN_VERBATIM_HEADERS "NO")
  set(DOXYGEN_GENERATE_HTML "NO")
  set(DOXYGEN_GENERATE_LATEX "NO")
  set(DOXYGEN_GENERATE_XML "YES")  
  doxygen_add_docs(doxygen src include)
endif()
