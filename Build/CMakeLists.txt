cmake_minimum_required(VERSION 3.9 FATAL_ERROR)
project(AK_Engine CXX)

option(BUILD_TESTS "Flag to determine whether to build tests or not" ON)

set(ENGINE_BINARY_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../Binaries)

set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${ENGINE_BINARY_PATH}/lib)
set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${ENGINE_BINARY_PATH}/lib)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${ENGINE_BINARY_PATH}/bin)

set(ENGINE_ROOT_PATH ${CMAKE_CURRENT_SOURCE_DIR}/../Engine)

add_subdirectory(${ENGINE_ROOT_PATH}/Editor Editor)

if(BUILD_TESTS)
    add_subdirectory(${ENGINE_ROOT_PATH}/Tests Tests)
endif()