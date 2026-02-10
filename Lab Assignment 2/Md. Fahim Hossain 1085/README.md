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
                                   "   FragColor = vec4(0.0f, 1.0f, 1.0f, 1.0f);\n"
                                   "}\n\0";

```

- Outputs a **cyan color** for all fragments
- Color used: `(0.0f, 1.0f, 1.0f, 1.0f)`

---

## Triangle Vertex Coordinates

```cpp
float vertices[] = {
    // Bottom-left obtuse triangle
    -0.9f, -0.8f, 0.0f,
    -0.2f, -0.8f, 0.0f,
    -0.9f, -0.3f, 0.0f,

    // Top-right obtuse triangle
     0.2f,  0.8f, 0.0f,
     0.9f,  0.8f, 0.0f,
     0.9f,  0.3f, 0.0f
};
```

These vertex coordinates ensure that:

- The two triangles are positioned **far apart** at opposite corners of the screen.
- Each triangle has **one obtuse angle**, satisfying the lab task requirement.

### Background Color

An **orange background** is applied using the following OpenGL function:

```cpp
glClearColor(1.0f, 0.5f, 0.0f, 1.0f);
```

### Window Creation

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

### Keyboard Input Handling

- Keyboard input is handled using the `processInput` function.
- When the user presses the **'F'** key (the first letter of the name \"Fahim\"), the window is closed.

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

#### Window Closing

![Window Closing on Key Press](./../closing%20window.gif)
