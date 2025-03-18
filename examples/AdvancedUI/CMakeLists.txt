# Define the example executable
add_executable(AdvancedUI AdvancedUI.cpp)

# Link with PictorUI
target_link_libraries(AdvancedUI PRIVATE PictorUI)

# Install example if desired
install(TARGETS AdvancedUI
    RUNTIME DESTINATION bin/examples
)