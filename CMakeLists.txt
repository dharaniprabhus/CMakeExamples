cmake_minimum_required(VERSION 3.10)

# set the project name
project(calc)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/modules")
message("path :" "${CMAKE_MODULE_PATH}")
include(PrintCMakeVars)

add_subdirectory(app)

print_all_vars()
