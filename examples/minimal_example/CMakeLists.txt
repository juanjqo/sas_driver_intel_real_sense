cmake_minimum_required(VERSION 3.16)

project(minimal_example LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


set(REPOSITORY_DIR ${CMAKE_CURRENT_SOURCE_DIR}/../../)
include_directories(${REPOSITORY_DIR}/software/include/)
include(${REPOSITORY_DIR}/dependencies.cmake)

#find_package(realsense2 REQUIRED)
find_package(Threads REQUIRED)

add_executable(minimal_example main.cpp)

#target_link_libraries(minimal_example  ${realsense2_LIBRARY})
target_link_libraries(minimal_example
    realsense2
    Threads::Threads
    glfw
    "-framework Cocoa"
    "-framework OpenGL"
    "-framework IOKit"
)
