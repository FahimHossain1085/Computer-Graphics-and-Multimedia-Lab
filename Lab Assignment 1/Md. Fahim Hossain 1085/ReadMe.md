# OpenGL GLFW Lab Assignment

## Assignment Objective

The objective of this lab assignment is to create a GLFW window with a cyan-colored background and set the window title to the student’s full name. Additionally, the program should close the window when the user presses the first letter of the student’s name on the keyboard.

---

## Assignment Requirements

1. Create a window with a cyan background color.
2. Set the window title to the student’s full name.
3. Close the window when the user presses the first letter of the student’s name.

---

## Implementation Details

### Window Creation

- The window is created using `glfwCreateWindow`.
- The window title is set to **"Md. Fahim Hossain"**, which satisfies the assignment requirement.

```cpp
GLFWwindow *window = glfwCreateWindow(
    SCR_WIDTH,
    SCR_HEIGHT,
    "Md. Fahim Hossain",
    NULL,
    NULL
);

```
