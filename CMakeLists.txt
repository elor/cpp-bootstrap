cmake_minimum_required(VERSION 3.14 FATAL_ERROR)
project(CppBootstrap)

include(cmake/CPM.cmake)

cpmaddpackage("gh:fmtlib/fmt#10.1.0")
cpmaddpackage("gh:catchorg/Catch2@3.4.0")

add_executable(main src/main.cpp)
target_link_libraries(main fmt::fmt)

enable_testing()
add_executable(test_fmt test/test_something.cpp)
target_link_libraries(test_fmt Catch2::Catch2WithMain fmt::fmt)
add_test(NAME test_fmt COMMAND test_fmt)
