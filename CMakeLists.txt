cmake_minimum_required(VERSION 3.14)
project(PictorUI VERSION 0.1.0 LANGUAGES CXX)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# Include FetchContent module
include(FetchContent)

# Declare Pictor dependency
FetchContent_Declare(
    pictor
    GIT_REPOSITORY https://github.com/TBTerra/pictor.git
    GIT_TAG master  # Consider using a specific tag or commit for stability
)

# Make Pictor available
FetchContent_MakeAvailable(pictor)

# Add include directories
include_directories(
    ${CMAKE_CURRENT_SOURCE_DIR}/include
    ${pictor_SOURCE_DIR}/include
)

# Add the source directory
add_subdirectory(src)

# Build examples if enabled
option(BUILD_EXAMPLES "Build example programs" ON)
if(BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()

# Build tests if enabled
option(BUILD_TESTS "Build tests" ON)
if(BUILD_TESTS)
    enable_testing()
    add_subdirectory(tests)
endif()

# Create library target
add_library(PictorUI
    $<TARGET_OBJECTS:pictorui_core>
)

# Link with Pictor
target_link_libraries(PictorUI PUBLIC pictor)

# Installation rules
install(TARGETS PictorUI
    LIBRARY DESTINATION lib
    ARCHIVE DESTINATION lib
    RUNTIME DESTINATION bin
)

# Install headers
install(DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/include/
    DESTINATION include
)