cmake_minimum_required(VERSION 3.13)  # CMake version check

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

project(palindrome)

find_package(GTest REQUIRED)

include_directories(../submission/include/)

enable_testing()

add_executable(
  palindrome_test
  palindrome_test.cpp ../submission/src/palindrome.cpp
)

target_link_libraries(
  palindrome_test
  GTest::gtest_main
)

include(GoogleTest)
gtest_discover_tests(palindrome_test)
