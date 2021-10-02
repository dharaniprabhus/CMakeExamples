cmake_minimum_required(VERSION 3.10)

set(ENABLE_DEBUG OFF PARENT_SCOPE)
set(ARITH_VERSION "1.0" CACHE STRING "1.0;1.1;1.2")
message(STATUS "ENABLE_DEBUG  : ${ENABLE_DEBUG} : ${CMAKE_CURRENT_LIST_FILE}")
message(STATUS "ARITH_VERSION  : ${ARITH_VERSION} : ${CMAKE_CURRENT_LIST_FILE}")

add_library(arith SHARED
   include/arith.h
   src/arith.cpp
)

target_include_directories(arith PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}/include"
)
