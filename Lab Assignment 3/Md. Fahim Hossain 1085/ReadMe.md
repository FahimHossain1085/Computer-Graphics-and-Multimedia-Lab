# Lab Assignment 3

## Implemented Features

- One **star** drawn using OpenGL

- **Cyan color** applied to the triangles using a fragment shader
- **Yellow background** applied using `glClearColor`
- Window title set to **"0432320005101085"**
- Window closes when the user presses **'f'** (initial of _Fahim_)

---

## Shader Implementation

### Vertex Shader

```cpp
const char *vertexShaderSource = "#version 330 core\n"
                                 "layout (location = 0) in vec3 aPos;\n"
                                 "void main()\n"
                                 "{\n"
                                 "   gl_Position = vec4(aPos.x, aPos.y, aPos.z, 1.0);\n"
                                 "}\0";

```

- Accepts vertex positions as input
- Passes positions directly to the OpenGL pipeline

### Fragment Shader

```cpp

const char *fragmentShaderSource = "#version 330 core\n"
    "out vec4 FragColor;\n"
    "void main()\n"
    "{\n"
    "   FragColor = vec4(0.0f, 1.0f, 1.0f, 1.0f);\n" //applying cyan color to the triangles
    "}\n\0";

```

- Outputs a **cyan color** for all fragments
- Color used: `(0.0f, 1.0f, 1.0f, 1.0f)`

---

## Triangle Vertex Coordinates

```cpp
float vertices[] = {
    // Triangle 1 Main body
     0.0f,  0.5f, 0.0f,  // Top point
    -0.3f, -0.4f, 0.0f,  // Bottom left point
     0.3f, -0.4f, 0.0f,  // Bottom right point

    // Triangle 2: Left arm
    -0.5f,  0.2f, 0.0f,  // Left point
     0.0f,  0.2f, 0.0f,  // Center top
     0.0f, -0.2f, 0.0f,  // Center bottom

    // Triangle 3: Right arm
     0.5f,  0.2f, 0.0f,  // Right point
     0.0f,  0.2f, 0.0f,  // Center top
     0.0f, -0.2f, 0.0f   // Center bottom
};
```

These vertex coordinates ensure that:

- Tiangle 1 Main body is positioned **center** of the screen.
- Each triangle placed appropriately to make **star shape **, satisfying the lab task requirement.

### Background Color

An **Yellow background** is applied using the following OpenGL function:

```cpp
glClearColor(1.0f, 1.0f, 0.0f, 1.0f);;
```

### Window Creation

- The window is created using `glfwCreateWindow`.
- The window title is set to **"0432320005101085"**.

```cpp
GLFWwindow *window = glfwCreateWindow(
    SCR_WIDTH,
    SCR_HEIGHT,
    "0432320005101085",
    NULL,
    NULL
);

```

### Keyboard Input Handling

- Keyboard input is handled using the `processInput` function.
- When the user presses the **'f'** key (the first letter of the name \"Fahim\"), the window is closed.

```cpp
void processInput(GLFWwindow *window)
{
    if (glfwGetKey(window, GLFW_KEY_F) == GLFW_PRESS)
        glfwSetWindowShouldClose(window, true);
}
```

### Screenshots

The following screenshots demonstrate the successful execution of the program:

#### Window Creation

![](./../output%20screenshot.JPG)
