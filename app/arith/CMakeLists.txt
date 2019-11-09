cmake_minimum_required(VERSION 3.10)

project(arith)

add_library(arith SHARED
   include/arith.h
   src/arith.cpp
)

target_include_directories(arith PUBLIC
    "${PROJECT_SOURCE_DIR}/include"
)
