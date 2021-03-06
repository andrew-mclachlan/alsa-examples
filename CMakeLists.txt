# Quick start guide to building with CMake.
#
# Download, install and add CMake to you PATH ( https://cmake.org/download ).
#
# For Windows, do:
#   cd build
#   cmake .. -G "Visual Studio 10 2010" (for VS2010)
#     or
#   cmake .. -G "Visual Studio 14 2015" (for VS2015)
#   cmake --build . --config Release
#
# For Unix, do:
#   cd build
#   cmake .. -DCMAKE_BUILD_TYPE=Release
#   cmake --build .

cmake_minimum_required (VERSION 3.5)
project(alsa-examples)

set(SOURCES 
    ../src/main.cxx)

set(HEADERS
    ../inc/main.h)

add_executable(${PROJECT_NAME} ${SOURCES} ${HEADERS})

include_directories(../inc)

set_target_properties(${PROJECT_NAME} PROPERTIES OUTPUT_NAME "alsa-examples")

find_package(ALSA REQUIRED asound)
target_link_libraries(${PROJECT_NAME} ${ALSA_LIBRARIES})

include_directories(${ALSA_INCLUDE_DIRS})

target_compile_definitions(${PROJECT_NAME} PUBLIC
                            UNIX)

set_target_properties(${PROJECT_NAME} PROPERTIES COMPILE_FLAGS "-Werror")
    
set(CMAKE_CXX_FLAGS "-std=c++11")

target_link_libraries(${PROJECT_NAME})
