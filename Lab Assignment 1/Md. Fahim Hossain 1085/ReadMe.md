<!-- # Setup

## 1.  Windows ##

   * ### Download glfw libray from https://www.glfw.org/download.html. Download *64-bit Windows binaries* from *Windows pre-compiled binaries*. ###
   * ### Create **build** and **lib** folder in Code Repo. Put *glfw3.dll* from *lib-mingw-w64* folder of glfw library to **build** and **lib** folder.  ###
   * ### For C++ compiler and make, Download MSYS2 Package Manager from https://www.msys2.org/ . ###
   * ### Run following commands in MSYS2 terminal: ```pacman -S base-devel``` and ```pacman -S gcc``` . ###
   * ### add your bin folder (which includes g++.exe and make.exe) PATH (C:\msys64\usr\bin) of msys64 installation directory in your environment variable.
   * ### Run ```make win``` in Terminal. ###
   * ### ```.exe``` file will be in **build** folder. ###
   * ### if your code does not run, then you have to check openGL version by installing GLview from http://www.realtech-vr.com/home/glview . If your openGL version is below 3.3, then update windows. ###
​
## 2. Linux ##

   * ### Run following command in Terminal:  ```sudo apt-get install libglfw3-dev``` ###
   * ### Create **build** and **lib** folder in Code Repo. ###
   * ### Run ```make linux``` in terminal. ###
   * ### executable file will be in **build** folder. ### -->

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
