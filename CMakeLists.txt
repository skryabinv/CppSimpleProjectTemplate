cmake_minimum_required(VERSION 3.16)
project(
  CppSimpleProjectTemplate
  VERSION 1.0.0
  LANGUAGES CXX C)

# Генерация compile_commands.json для IntelliSense
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(CMAKE_C_STANDARD 11)
set(CMAKE_C_STANDARD_REQUIRED ON)

include(cmake/ClangTidy.cmake)
include(cmake/CPM.cmake)

CPMAddPackage(
  NAME googletest URL
  https://github.com/google/googletest/archive/refs/tags/v1.17.0.zip VERSION
  1.17.0)

# add_subdirectory(3rdparty/...)

# add_subdirectory(3rdparty/...)

add_subdirectory(src)

enable_testing()
add_subdirectory(tests)
