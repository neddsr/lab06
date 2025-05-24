cmake_minimum_required(VERSION 3.10)
project(hello_world_application)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_executable(hello_world_application ${CMAKE_CURRENT_SOURCE_DIR}/hello_world.cpp)

target_include_directories(hello_world_application PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/../formatter_ex_lib)
target_link_libraries(hello_world_application formatter_ex_lib)
