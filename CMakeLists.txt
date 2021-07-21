cmake_minimum_required(VERSION 3.13)

project(sample-NeoC
    VERSION 1.0
    DESCRIPTION "NeoC Sample Project"
    LANGUAGES C
)

# guard against in-source builds
if(${CMAKE_SOURCE_DIR} STREQUAL ${CMAKE_BINARY_DIR})
    message(FATAL_ERROR "In-source builds not allowed. Please make a new directory (called a build directory) and run CMake from there. You may need to remove CMakeCache.txt. ")
endif()

# Build libNeoC
include(FetchContent)
FetchContent_Declare(
    NeoC
    GIT_REPOSITORY https://github.com/RotationE/NeoC.git
    GIT_TAG        origin/main
)

FetchContent_GetProperties(NeoC)
if(NOT neoc_POPULATED)
    FetchContent_Populate(NeoC)
    add_subdirectory(${neoc_SOURCE_DIR} ${neoc_BINARY_DIR})
endif()

add_subdirectory(src)
