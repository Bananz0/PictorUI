# Define the example executable
add_executable(BasicUI BasicUI.cpp)

# Link with PictorUI
target_link_libraries(BasicUI PRIVATE PictorUI)

# Install example if desired
install(TARGETS BasicUI
    RUNTIME DESTINATION bin/examples
)