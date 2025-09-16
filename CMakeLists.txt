cmake_minimum_required(VERSION 3.10)

project(CountingSDK)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(include)

file(GLOB SOURCES "src/*.cpp")

add_library(counting_sdk ${SOURCES})
target_include_directories(counting_sdk PUBLIC include)

# testing
enable_testing()
add_subdirectory(tests)