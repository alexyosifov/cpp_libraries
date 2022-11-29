cmake_minimum_required(VERSION 3.6)
project(UseLibs)

set(BINARY_NAME "UseLibs")

set(CMAKE_CXX_FLAGS "-Wall -std=c++17")

set(SOURCE_FILES main.cpp)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}"
                    libs)

add_executable(${BINARY_NAME}
    main.cpp)

target_link_libraries(${BINARY_NAME}
    ${CMAKE_SOURCE_DIR}/libs/build/libMath_.so)