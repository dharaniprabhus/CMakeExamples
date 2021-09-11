cmake_minimum_required(VERSION 3.10)

add_library(exp STATIC
   include/exp.h
   src/exp.cpp
)

target_include_directories(exp 
	PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/include"
)
