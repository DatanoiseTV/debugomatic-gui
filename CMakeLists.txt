cmake_minimum_required(VERSION 3.10)
project(OSCape)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

INCLUDE_DIRECTORIES(${PROJECT_SOURCE_DIR})


add_subdirectory("dep")

SET(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin) 
SET(CMAKE_CXX_FLAGS "-O2")

include_directories(${GLFW3_INCLUDE_DIRS})
add_executable(OSCape main.cpp)
target_link_libraries(OSCape PRIVATE IMGUI)
add_custom_target (run COMMAND ${EXECUTABLE_OUTPUT_PATH}/OSCape)
