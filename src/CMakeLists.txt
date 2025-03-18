# Define the core library object
add_library(pictorui_core OBJECT
    Components/Window.cpp
    Components/Button.cpp
    Components/Label.cpp
    Components/Container.cpp
    Components/TextField.cpp
    Components/ImageView.cpp
    Layouts/Layout.cpp
    Layouts/VerticalLayout.cpp
    Layouts/HorizontalLayout.cpp
    Layouts/GridLayout.cpp
    Events/EventHandler.cpp
)

# Set include directories for this target
target_include_directories(pictorui_core
    PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}
    PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/../include
)

# Link with Pictor for implementation files
target_link_libraries(pictorui_core PRIVATE pictor)