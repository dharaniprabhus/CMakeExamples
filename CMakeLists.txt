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

#updating a variable in a function
function (add_item items)
    list(APPEND ${items} green)
    set(${items} ${${items}} PARENT_SCOPE)
endfunction()

function(print_vars items)
    foreach(item ${${items}})
        message("${item}")
    endforeach()
endfunction()

set (colors red blue)
add_item(colors)
print_vars(colors)

print_all_files()

#variables
set(MYBOOLON ON)
set(MYBOOLOFF OFF)
set(MYSTR "foo")
set(MYID 10)

if (MYBOOLON)
    message(MYBOOLON " set")
endif()

if (MYBOOLOFF)
    message(MYBOOLOFF " set")
endif()

if (MYSTR)
    message(MYSTR " set")
endif()

if (MYSTR STREQUAL "foo")
    message(${MYSTR} " = foo")
endif()

if (NOT MYSTR STREQUAL "bar")
    message(${MYSTR} " != bar")
endif()

if (MYSTR MATCHES "f.*")
    message(${MYSTR} " matches expression f.*")
endif()

if (MYID EQUAL 10)
    message(${MYID} " = 10")
endif()

if (MYID LESS 10)
    message(${MYID} " < 10")
endif()

if (MYID GREATER 10)
    message(${MYID} " > 10")
endif()

set(CMAKE_MODULE_PATH "${CMAKE_SOURCE_DIR}/modules")
include(PrintCMakeVars)

add_subdirectory(app)

# print_all_vars()
