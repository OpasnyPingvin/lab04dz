cmake_minimum_required(VERSION 3.4)
project(solver)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib formatter_build)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib formatter_ex_build)
add_subdirectory(${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib solver_lib_build)

add_executable(solver
	${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp
)

target_include_directories(solver PRIVATE
	${CMAKE_CURRENT_SOURCE_DIR}
	${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib
	${CMAKE_CURRENT_SOURCE_DIR}/../formatter_lib
	${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib
)

target_link_libraries(solver PRIVATE
	formatter_ex
	solver_lib
)
