cmake_minimum_required(VERSION 3.10)

project(example)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(OpenCV REQUIRED)

include_directories(${OpenCV_INCLUDE_DIRS})

add_executable(example src/main.cpp)

target_link_libraries(example ${OpenCV_LIBS})