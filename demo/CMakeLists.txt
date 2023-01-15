cmake_minimum_required(VERSION 3.24)
project(demo C)

set(CMAKE_C_STANDARD 17)


add_executable(demo main.c glad.c)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)
include_directories(include)
add_subdirectory(lib/glfw-3.3.8)
target_link_libraries(demo glfw)
find_package(OpenGL REQUIRED)
target_link_libraries(demo OpenGL::GL)