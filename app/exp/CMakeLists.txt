cmake_minimum_required(VERSION 3.10)

project(exp)

add_library(exp STATIC
   include/exp.h
   src/exp.cpp
)

target_include_directories(exp 
	PUBLIC
        "${PROJECT_SOURCE_DIR}/include"
)
