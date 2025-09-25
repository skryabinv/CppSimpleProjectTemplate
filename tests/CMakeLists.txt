include(FetchContent)
include(GoogleTest)

add_executable(tests test_example.cpp)
target_link_libraries(tests PRIVATE GTest::gtest_main)

AddClangTidy(tests)

gtest_discover_tests(tests)
