# Lab Assignment 5

## Implemented Features

- Rectangle drawn using two triangles with OpenGL
- Dynamic color animation using a fragment shader (red to white transition)
- Transformation effects: scaling and rotation applied in real-time
- Dark gray background (0.1, 0.1, 0.1) applied using glClearColor
- Window title set to "0432320005101085"
- Smooth animation using sin function for time-based effects

---

## Color Animation Logic

```cpp
float timeValue = glfwGetTime();
float mixValue = (sin(timeValue) * 0.5f + 0.5f); // oscillates 0→1
float r = 1.0f;
float g = mixValue;
float b = mixValue;
```

- Creates smooth transition from red (1, 0, 0) to white (1, 1, 1)
- Produces continuous animation effect using sine wave oscillation
- Red component stays constant at 1.0, green and blue blend from 0 to 1

---

## Transformation Logic

```cpp
float scale = 0.5f + 0.5f * sin(timeValue); // magnify
float angle = timeValue; // rotate over time
float cosA = cos(angle), sinA = sin(angle);

float transform[16] = {
    scale * cosA, scale * -sinA, 0.0f, 0.0f,
    scale * sinA, scale *  cosA, 0.0f, 0.0f,
    0.0f,         0.0f,         scale, 0.0f,
    0.0f,         0.0f,         0.0f,  1.0f
};
```

- Rectangle scales between 0.0 and 1.0 over time
- Rectangle rotates continuously based on elapsed time
- Applied via transformation matrix passed to vertex shader

---
