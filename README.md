# PictorUI

PictorUI is a **declarative UI framework for C++**, built to work seamlessly with **Pictor**. It allows developers to create user interfaces using a simple and expressive API while leveraging Pictor for efficient rendering.

## Features

* **Declarative API** – Define UI layouts in a clean, readable manner
* **Component-Based** – Window, Buttons, Containers, Labels, and more
* **Event Handling** – Bind user interactions using lambda functions
* **Flexible Layouts** – Support for Vertical, Horizontal, and Grid layouts
* **Optimized Rendering** – Uses Pictor for efficient drawing and performance

## Installation

```bash
# Clone the repository
git clone https://github.com/yourusername/PictorUI.git
cd PictorUI

# Build the project (CMake recommended)
mkdir build && cd build
cmake ..
make
```

## Usage

### Creating a Simple UI

```cpp
#include "PictorUI.h"

int main() {
    UI::Window("My App", 800, 600)
        .add(UI::Container(Layout::Vertical)
            .add(UI::Label("Welcome to PictorUI"))
            .add(UI::Button("Click Me").onClick([] { std::cout << "Clicked!\n"; }))
        )
        .show();
}
```

## Core Components

### UI Elements

* **Window** – Main application window
* **Container** – Holds and organizes UI elements
* **Label** – Displays text
* **Button** – Clickable element
* **TextField** – User input field
* **ImageView** – Displays images

### Layout System

* **Vertical Layout** – Stack elements from top to bottom
* **Horizontal Layout** – Arrange elements side by side
* **Grid Layout** – Define rows and columns for placement

### Event Handling

Bind interactions using lambdas:

```cpp
Button("Click Me").onClick([] { std::cout << "Button Pressed!\n"; });
```

## Roadmap

* Simple Mockup
* Actual Implementation
* Further testing

## Contributing

Contributions are welcome! Open an issue or create a pull request to help improve PictorUI.

## License

MIT License
