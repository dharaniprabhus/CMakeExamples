cmake_minimum_required(VERSION 3.10)

add_subdirectory(exp)
add_subdirectory(arith)

add_executable(calc
	main.cpp)

target_link_libraries(calc
PRIVATE
    arith
    exp
)
