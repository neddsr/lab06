cmake_minimum_required(VERSION 3.10)
project(solver_application)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(solver_application ${CMAKE_CURRENT_SOURCE_DIR}/equation.cpp)

target_include_directories(formatter_ex_lib PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib 
${CMAKE_CURRENT_SOURCE_DIR}/../solver_lib)
target_link_libraries(solver_application formatter_ex_lib solver_lib)
