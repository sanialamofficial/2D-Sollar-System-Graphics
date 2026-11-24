# 2D Solar System Simulation (OpenGL & FreeGLUT)

An interactive 2D Solar System simulation built in C++ using legacy OpenGL and FreeGLUT. This project models planetary orbits, hierarchical moon systems, a dynamic asteroid belt, twinkling background stars, and periodic shooting stars with real-time camera controls.

---

## Features & What's Inside

* **Complete Planetary System:** Models the Sun and all 8 major planets (Mercury through Neptune) with distinct sizes, color profiles, orbital radii, and relative orbital speeds (including retrograde rotation for Venus).
* **Hierarchical Moon Orbits:** Uses nested matrix transformations (`glPushMatrix` / `glPopMatrix`) to render moons orbiting Earth (1), Mars (2), Jupiter (4), Saturn (1), Uranus (1), and Neptune (1).
* **Dynamic Asteroid Belt:** Generates 800 individual asteroids positioned between Mars and Jupiter with continuous orbital drift.
* **Atmospheric Space Environment:**
  * Deep-space gradient backdrop (`GL_QUADS`).
  * 400 procedurally placed stars with sine-wave alpha twinkling animations.
  * Randomized shooting stars that streak across the viewport periodically.
* **On-Screen HUD & Labels:** Toggleable planet name labels and control hints rendered via GLUT bitmap fonts (`GLUT_BITMAP_8_BY_13`).
* **Delta-Time Animation Loop:** Uses frame-delta timing (`glutGet(GLUT_ELAPSED_TIME)`) clamped for stability to ensure consistent simulation speeds across different hardware refresh rates.

---

## Tech Stack & Libraries Used

* **Language:** C++
* **Graphics API:** OpenGL (`GL/gl.h`, `GL/glu.h`) — 2D orthographic projection (`glOrtho`), matrix stack transformations, and alpha blending.
* **Windowing & Input:** FreeGLUT / GLUT (`GL/glut.h`) — window management, double-buffered rendering (`GLUT_DOUBLE`), timer callbacks, and keyboard event handling.
* **Standard Libraries:** `<cmath>` (trigonometric orbit/circle calculations), `<cstdlib>`, `<ctime>` (procedural starfield, asteroid belt, and shooting star generation).

---

## Controls

| Key | Action |
| :--- | :--- |
| **Arrow Keys** (`↑` `↓` `←` `→`) | Pan the camera view across the solar system |
| **`+` / `-`** | Zoom in and out (`0.1x` to `4.0x`) |
| **`Space`** | Pause or resume planetary motion |
| **`I`** | Toggle planet names and on-screen control HUD |
| **`0`** | Reset camera zoom and position to default |

---

## How to Build & Run

### Windows (MinGW / g++)
Ensure FreeGLUT is installed and linked in your compiler path:

```bash
g++ main.cpp -o SolarSystem.exe -lfreeglut -lopengl32 -lglu32
./SolarSystem.exe
```

### Linux (Ubuntu / Debian)
1. Install the required OpenGL and FreeGLUT development packages:
   
```bash
sudo apt update
sudo apt install build-essential freeglut3-dev

2. Compile and run:
```bash
g++ main.cpp -o solar_system -lGL -lGLU -lglut
./solar_system
```

## Project Structure

```text
├── main.cpp        # Complete source code (data structs, rendering, physics update, input callbacks)
└── README.md       # Project documentation
```
## Interface:
 

https://github.com/user-attachments/assets/dc1823a5-e736-456a-bf6e-2b28f30d28f3



