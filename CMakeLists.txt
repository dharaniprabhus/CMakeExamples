cmake_minimum_required(VERSION 3.10)

# set the project name
project(calc)



function(print_all_files)
# bring all files to variable all_files
    file(GLOB_RECURSE all_files ${PROJECT_SOURCE_DIR}/*.cpp ${PROJECT_SOURCE_DIR}/*.h)
# a list is a semicola or space separated
    message ("List ${all_files}")
    foreach(fname ${all_files})
        message("Full file name : ${fname}")
        get_filename_component(component_name "${fname}" NAME)
        message("File name : ${component_name}")
    endforeach()
endfunction()

function(print_vars items)
    foreach(item ${${items}})
        message("${item}")
    endforeach()
endfunction()

set (colors red blue)
print_all_files()
print_vars(colors)

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/modules")
include(PrintCMakeVars)

add_subdirectory(app)

# print_all_vars()
