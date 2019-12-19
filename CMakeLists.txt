# cmake_minimum_required(VERSION <specify CMake version here>)
cmake_minimum_required(VERSION 3.15)

project(pzdc)
find_package(OpenGL REQUIRED)
set(CMAKE_CXX_STANDARD 20)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(glfw)

include_directories(glfw/include)

add_executable(pzdc src/main.cpp)

target_link_libraries(pzdc glfw)
target_link_libraries(pzdc -static-libgcc)
target_link_libraries(pzdc -static-libstdc++)
target_link_libraries(pzdc ${OPENGL_gl_LIBRARY})
