cmake_minimum_required(VERSION 3.4)
project(hello_world)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(FORMATTER_LIB ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib)
set(FORMATTER_EX_LIB ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)

add_executable(hello_world hello_world.cpp)

target_include_directories(hello_world PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}
	${FORMATTER_EX_LIB}
	${FORMATTER_LIB}
)       

target_link_libraries(hello_world PRIVATE 
	${FORMATTER_EX_LIB}/build/libformatter_ex.a
	${FORMATTER_LIB}/build/libformatter.a
)
