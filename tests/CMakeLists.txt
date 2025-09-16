cmake_minimum_required(VERSION 3.14)

project(counting_sdk_tests)

# Enable testing
enable_testing()
include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/03597a01ee50ed33e9dfd640b249b4be3799d395.zip
)
# For Windows: Prevent overriding the parent project's compiler/linker settings
set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

# Add test source files
set(TEST_SOURCES
    main.cpp
    # Add more test files here
)

add_executable(counting_sdk_tests ${TEST_SOURCES})

target_link_libraries(counting_sdk_tests PRIVATE GTest::gtest GTest::gtest_main)

# Optionally, include directories if needed
# target_include_directories(counting_sdk_tests PRIVATE ../include)

add_test(NAME counting_sdk_tests COMMAND counting_sdk_tests)