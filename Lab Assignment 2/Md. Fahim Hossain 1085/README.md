# Lab Assignment 2

## Implemented Features

- Two **obtuse triangles** drawn using OpenGL
- Triangles are positioned at:
  - Bottom-left corner
  - Top-right corner
- **Cyan color** applied to the triangles using a fragment shader
- **Orange background** applied using `glClearColor`
- Window title set to **"Md. Fahim Hossain"**
- Window closes when the user presses **'F'** (initial of _Fahim_)

<!-- ### Window Creation

- The window is created using `glfwCreateWindow`.
- The window title is set to **"Md. Fahim Hossain"**.

```cpp
GLFWwindow *window = glfwCreateWindow(
    SCR_WIDTH,
    SCR_HEIGHT,
    "Md. Fahim Hossain",
    NULL,
    NULL
);

```

### Background Color

- The background color of the window is set to **cyan** using RGBA values.
- The color buffer is cleared every frame to apply the cyan color.

```cpp
glClearColor(0.0f, 1.0f, 1.0f, 1.0f);
glClear(GL_COLOR_BUFFER_BIT);
```

### Keyboard Input Handling

- Keyboard input is handled using the `processInput` function.
- When the user presses the **'F'** key (the first letter of the name \"Fahim\"), the window is closed.

```cpp
void processInput(GLFWwindow *window)
{
    if (glfwGetKey(window, 'F') == GLFW_PRESS)
        glfwSetWindowShouldClose(window, true);
}
```

### Screenshots

The following screenshots demonstrate the successful execution of the program:

- A cyan-colored window is displayed upon running the application.
- The window title shows the full name **"Md. Fahim Hossain"**.
- Pressing the **'F'** key closes the window as required.

### Example Screenshots

#### Window Creation

![Cyan Window with Name](./../output%20screenshot.jpg)

#### Window Closing

![Window Closing on Key Press](./../closing%20window.gif) -->
