# Lab Assignment 4

## Implemented Features

- One triangle drawn using OpenGL
- Dynamic color animation applied using a fragment shader (cyan to magenta transition)
- White color applied when pressing 'W'
- Red color lock enabled when pressing 'R'
- Blue background applied using glClearColor
- Window title set to "0432320005101085"
- Window closes when the user presses 'F' (initial of Fahim)

---

## Color Animation Logic



```cpp
float blendValue = sin(timeValue) * 0.5 + 0.5;

```

- Creates smooth transition between colors
- Produces continuous animation effect


### Keyboard Input Handling
- Keyboard input is handled using the processInput function

```cpp
 while (!glfwWindowShouldClose(window))
    {
        // input
        // -----
        processInput(window);

        // render
        // ------
        glClearColor(0.0f, 0.0f, 1.0f, 1.0f);
        glClear(GL_COLOR_BUFFER_BIT);

        // be sure to activate the shader before any calls to glUniform
        glUseProgram(shaderProgram);

        // update shader uniform
        double timeValue = glfwGetTime(); 
        float blendValue = static_cast<float>(sin(timeValue) * 0.5 + 0.5);
        int vertexColorLocation = glGetUniformLocation(shaderProgram, "ourColor");

        if (gRedLocked)
        {
            glUniform4f(vertexColorLocation, 1.0f, 0.0f, 0.0f, 1.0f);
        }
        else if (glfwGetKey(window, GLFW_KEY_W) == GLFW_PRESS)
        {
            glUniform4f(vertexColorLocation, 1.0f, 1.0f, 1.0f, 1.0f);
        }
        else
        {
            // Animate cyan (0,1,1) to magenta (1,0,1)
            glUniform4f(vertexColorLocation, blendValue, 1.0f - blendValue, 1.0f, 1.0f);
        }


        // render the triangle
        glDrawArrays(GL_TRIANGLES, 0, 3);

        // glfw: swap buffers and poll IO events (keys pressed/released, mouse moved etc.)
        // -------------------------------------------------------------------------------
        glfwSwapBuffers(window);
        glfwPollEvents();
    }

    // optional: de-allocate all resources once they've outlived their purpose:
    // ------------------------------------------------------------------------
    glDeleteVertexArrays(1, &VAO);
    glDeleteBuffers(1, &VBO);
    glDeleteProgram(shaderProgram);

    // glfw: terminate, clearing all previously allocated GLFW resources.
    // ------------------------------------------------------------------
    glfwTerminate();
    return 0;
}

void processInput(GLFWwindow *window)
{
    if (glfwGetKey(window, GLFW_KEY_F) == GLFW_PRESS)
        glfwSetWindowShouldClose(window, true);

    if (glfwGetKey(window, GLFW_KEY_R) == GLFW_PRESS)
        gRedLocked = true;
}

```

- Press 'W' → Triangle becomes white
- Press 'R' → Triangle color locks to red
- Press 'F' → Window closes

---



