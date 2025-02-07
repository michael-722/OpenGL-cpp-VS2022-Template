# OpenGL VS Template (GLAD & GLFW, Relative Linking)

A Visual Studio 2022 C++ template that provides a basic setup for an OpenGL project using GLAD and GLFW. Everything is linked relatively—no system-wide installation of these libraries is required.

## Installation
1. Download the template ZIP from this repository.
2. Copy it into:```C:\Users<YOUR_USERNAME>\Documents\Visual Studio 2022\Templates\ProjectTemplates```
3. Restart Visual Studio if it’s already open.

## Usage
1. In Visual Studio 2022, go to **File → New → Project**.
2. Search for or select **"Blank OpenGL Window"** (or the name you see in the list).
3. Specify your project name and location, then click **Create**.

### Starter Project Includes:
- GLAD files under `dependencies/include/GLAD`
- GLFW headers under `dependencies/include/GLFW`
- A basic `main.cpp` and `glad.c` source

## **Important: Manually Add `glfw3.lib`**
Due to a quirk in Visual Studio’s template exporter, the `glfw3.lib` file is not automatically copied into your new project.

### Steps:
1. Go to the project folder in File Explorer:
```
YourProjectName
    └─ dependencies
        └─ lib
```
2. Manually copy `glfw3.lib` into the **lib** folder.
3. Build your project. The linker should now find `glfw3.lib` without errors.

> **Note:** This template does not include any GLFW DLL files. If you need them at runtime, please download or compile them separately.

## Why the Manual Copy?
Visual Studio sometimes excludes certain non-source files when creating templates, even if they’re included in the original project. In this case, `.lib` files aren’t brought over reliably. Until this limitation is resolved, you’ll need to copy `glfw3.lib` yourself.

## Credits
- **GLFW** for window and input handling.
- **GLAD** for OpenGL function loading.
