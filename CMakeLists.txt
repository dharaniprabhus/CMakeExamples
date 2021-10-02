cmake_minimum_required(VERSION 3.10)

# set the project name
project(calc)

# bring all files to variable all_files
file(GLOB_RECURSE all_files ${PROJECT_SOURCE_DIR}/*.cpp
    ${PROJECT_SOURCE_DIR}/*.h)

# a list is a semicola or space separated
message ("List ${all_files}")

foreach(fname ${all_files})
    message("File name : ${fname}")
endforeach()

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/modules")
include(PrintCMakeVars)

add_subdirectory(app)

# print_all_vars()
