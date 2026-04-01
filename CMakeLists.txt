cmake_minimum_required(VERSION 3.10)
project(FormatterInc)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Добавляем все подпроекты
add_subdirectory(formatter_lib)
add_subdirectory(solver_lib)
add_subdirectory(formatter_ex_lib)
add_subdirectory(hello_world_application)
add_subdirectory(solver_application)
