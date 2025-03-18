# Find test framework (Google Test is commonly used)
find_package(GTest REQUIRED)

# Components tests
add_executable(ButtonTest Components/ButtonTest.cpp)
target_link_libraries(ButtonTest PRIVATE PictorUI GTest::GTest GTest::Main)
add_test(NAME ButtonTest COMMAND ButtonTest)

# Layout tests
add_executable(LayoutTest Layouts/LayoutTest.cpp)
target_link_libraries(LayoutTest PRIVATE PictorUI GTest::GTest GTest::Main)
add_test(NAME LayoutTest COMMAND LayoutTest)

# If you want to run all tests with a single command
add_custom_target(check
    COMMAND ${CMAKE_CTEST_COMMAND} --verbose
    DEPENDS ButtonTest LayoutTest
)