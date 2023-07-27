cmake_minimum_required(VERSION 3.25)
project(pubgrub VERSION 0.3.1 LANGUAGES CXX)

include(FetchContent)

FetchContent_Declare(
        neo-fun
        GIT_REPOSITORY https://github.com/Chamber6821/neo-fun-cmake.git
        GIT_TAG 0.11.1-cmake
)

add_library(pubgrub INTERFACE)
target_include_directories(pubgrub INTERFACE src)
add_library(pubgrub::pubgrub ALIAS pubgrub)

FetchContent_MakeAvailable(neo-fun)
target_link_libraries(pubgrub INTERFACE neo::fun)
