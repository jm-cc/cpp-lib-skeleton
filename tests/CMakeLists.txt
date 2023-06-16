add_executable(hello hello.cpp)
target_link_libraries(hello cpp-lib-skeleton)

# Simple test, does it run ?
add_test(NAME HELLO_RUNS COMMAND hello)

