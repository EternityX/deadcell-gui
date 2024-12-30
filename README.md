# Notice
For a more feature complete project, see:
https://github.com/EternityX/deadcell-gui-2

# DEADCELL GUI
[![GitHub license](https://img.shields.io/badge/license-BSD3-red)](https://github.com/EternityX/DEADCELL-GUI/blob/master/LICENSE)

Unfortunately the DEADCELL 'remake' was never finished, therefore this GUI is lacking a lot of features. I believe it is a good base to build from into something nice. It features some nice things such as window managing, event handling, and some other small things.

Event-driven UI library for gamehacking. Platform and rendering independent code is handled by [ImGui](https://github.com/ocornut/imgui).

## Setup
Clone the project and submodules.
```
git clone --recurse-submodules --remote-submodules https://github.com/EternityX/deadcell-gui.git
```

Or clone the project and manually clone the submodules.

```
git clone https://github.com/EternityX/deadcell-gui.git
git submodule init
git submodule update
```

## Usage
1. Link and include the project
```cpp
#include <deadcell_gui.h>
```

2. Initialize
```cpp
auto dc_gui = std::make_shared<gui::deadcell_gui>();
```

3. Add a window
```cpp
auto main_window = dc_gui->add<gui::window>("Window title", "unique_window_id");
```

4. Add controls
```cpp
bool test_var = false;
auto checkbox1 = dc_gui->add<gui::checkbox>("Checkbox", "unique_checkbox_id", &test_var, [&]() {
    test_var = !test_var;
});

main_window->add_child(checkbox1);
```

4. Inside your render loop
```cpp
gui::drawing::set_draw_list(gui::drawing::draw_list_foreground);
dc_gui->new_frame();
```

## `imconfig.h`
Here are some recommended options to enable/disable in `imconfig.h`.

```cpp
#define IMGUI_DISABLE_OBSOLETE_FUNCTIONS
#define IMGUI_DISABLE_DEMO_WINDOWS
#define IMGUI_DISABLE_METRICS_WINDOW
#define IMGUI_DISABLE_FILE_FUNCTIONS
#define IMGUI_USE_WCHAR32
#define IMGUI_ENABLE_FREETYPE
```

