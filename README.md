# This project is superseded by [deadcell-gui-2](https://github.com/EternityX/deadcell-gui-2).

# Notice
Unfortunately the DEADCELL 'remake' was never finished, therefore this GUI is lacking a lot of features. I believe it is a good base to build from into something nice. It features some nice things such as window managing, event handling, and some other small things.

# DEADCELL GUI
[![GitHub license](https://img.shields.io/badge/license-BSD3-red)](https://github.com/EternityX/DEADCELL-GUI/blob/master/LICENSE)

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

# Design prototypes

Below are some bonus design prototypes I made which I intended to use for the DEADCELL project, please note that this is not actually included within this repository and is merely a design.

If you bought a menu design looking like the two prototypes below, thinking it was original, you got scammed.

### I (EternityX) do not permit others to use my intellectual property (DEADCELL), or other identifying marks or designs (this includes whole imitations). You may also not cover or obscure any part of the designs. Any other intellectual propery such as the skin images (found in the skins tab) or artwork (found within the scripts tab) of the design are not my property and is fair-use. This notice can be changed at any time.

![image](https://user-images.githubusercontent.com/4403000/230327126-c4c0a408-07c5-4616-9100-14e13b10fc75.png)

https://user-images.githubusercontent.com/4403000/230328040-339e8fe2-56c5-4dd9-8751-1960c956cc85.mp4

