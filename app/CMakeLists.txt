cmake_minimum_required(VERSION 3.10)

add_subdirectory(exp)
add_subdirectory(arith)

message(STATUS "ENABLE_DEBUG  : ${ENABLE_DEBUG} : ${CMAKE_CURRENT_LIST_FILE}")
message(STATUS "ARITH_VERSION  : ${ARITH_VERSION} : ${CMAKE_CURRENT_LIST_FILE}")

add_executable(calc
	main.cpp)

target_link_libraries(calc
PRIVATE
    arith
    exp
)
