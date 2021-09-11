cmake_minimum_required(VERSION 3.10)

add_library(arith SHARED
   include/arith.h
   src/arith.cpp
)

target_include_directories(arith PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/include"
)
