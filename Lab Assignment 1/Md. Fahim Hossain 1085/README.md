# Lab Assignment 1

## Assignment Objective

Create a dedicated GitHub Repository for this course and submit the folder link and output screenshot (full window) for this assignment. Add a proper README file. Follow proper code formatting. Add comments where necessary (Prove that it has been run in your computer). Your work must be original.

Create a cyan colored window containing your full name as the window name. If the user presses the keyboard's key "your name's first letter", the window gets closed.

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

#### Example Screenshots

##### Window Creation

![Cyan Window with Name](./../output%20screenshot.jpg)

##### Window Closing

![Window Closing on Key Press](./../closing%20window.gif)

> 📌 _These screenshots verify that all assignment requirements have been correctly implemented._
