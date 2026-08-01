#-----------------------------------------------------------------------------------------------------------------------
# Google Test
#-----------------------------------------------------------------------------------------------------------------------
include(GoogleTest)
enable_testing()

#-----------------------------------------------------------------------------------------------------------------------
# Target: cpp_set_test
# Alias: collections::cpp_set_test
# Type: Executable
# Dependencies: GTest::gtest_main, GTest::gmock_main, collections::cpp_set_headers
#-----------------------------------------------------------------------------------------------------------------------
# Target definition
add_executable(cpp_set_test)

# Target alias
add_executable(collections::cpp_set_test ALIAS cpp_set_test)

# Target sources
target_sources(cpp_set_test
    PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}/cpp_set_test.cpp
)

# Target dependencies
target_link_libraries(cpp_set_test
    PRIVATE
        collections::cpp_set_headers
        GTest::gtest_main
        GTest::gmock_main
)

# Test discovery
gtest_discover_tests(cpp_set_test)