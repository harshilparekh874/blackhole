# **Black Hole Visualizer**

A high-performance, real-time General Relativity simulator using C++ and OpenGL Compute Shaders. This project simulates the complex spacetime curvature around black holes, including gravitational lensing, accretion disks, and frame-dragging.

![Black Hole Simulation](https://via.placeholder.com/800x450?text=Black+Hole+Simulation) *(Generate your own stunning screenshots in-app!)*

## **🚀 New Features**

- **🌌 Procedural Starfield**: Accurate gravitational lensing visualization using a procedural noise-based background.
- **🌀 Kerr Metric Support**: Simulate rotating black holes with adjustable spin parameters and **Lense-Thirring frame-dragging**.
- **💥 Relativistic Doppler Shifting**: Real-time color shifting (blue-shift/red-shift) and relativistic beaming for the accretion disk.
- **☁️ Volumetric Accretion Disk**: Ray-marched volumetric gas simulation for a smoother, more realistic disk appearance.
- **🖥️ Interactive ImGui UI**: Real-time control panel to adjust physics, resolution, and rendering quality.
- **⚡ Performance Optimizations**:
  - **Adaptive Step Sizing**: RK4 integrator that scales steps based on distance from the singularity.
  - **Dynamic Resolution**: Automatically balances quality and FPS during camera movement.
  - **GPU Acceleration**: Heavy geodesic integration performed entirely in OpenGL Compute Shaders.

---

## **🎮 Controls**

### **Mouse**
- **Left Click + Drag**: Orbit the black hole.
- **Scroll**: Zoom in/out.
- **UI Sliders**: Adjust render scale, black hole spin, and gravity.

### **Keyboard Shortcuts**
- **`1` / `2`**: Decrease / Increase **Render Scale** (Quality vs speed).
- **`3` / `4`**: Decrease / Increase **Black Hole Spin** (Kerr parameter).
- **`5`**: Toggle **Performance Mode** (Dynamic resolution).
- **`G`**: Toggle **N-Body Gravity** simulation.

---

## **🛠 Building Requirements**

1. **C++ Compiler**: Supporting C++17 or newer.
2. **[CMake](https://cmake.org/)**: Version 3.21+.
3. **[Vcpkg](https://vcpkg.io/en/)**: For dependency management.
4. **[Git](https://git-scm.com/)**: For cloning and updating.

## **⚙️ Build Instructions**

1. **Clone the repository**:
   ```bash
   git clone https://github.com/kavan010/blackhole.git
   cd blackhole
   ```

2. **Install dependencies**:
   ```bash
   vcpkg install
   ```

3. **Configure and Build**:
   ```bash
   cmake -B build -S . -DCMAKE_TOOLCHAIN_FILE=[path_to_vcpkg]/scripts/buildsystems/vcpkg.cmake
   cmake --build build --config Release
   ```

4. **Run the program**:
   The executable will be located in `build/Release/BlackHole3D.exe`.

---

## **🔬 How it Works**

The simulation uses an **RK4 (Runge-Kutta 4th Order) integrator** to solve the null geodesic equations for light rays. 

- **Schwarzschild & Kerr Metrics**: The code integrates the path of light through curved spacetime.
- **Compute Shader**: All heavy-duty integration is performed in `geodesic.comp`, allowing for thousands of rays to be integrated in parallel.
- **UBO (Uniform Buffer Objects)**: Parameters like camera position, black hole mass, and spin are synced to the GPU every frame for interactive feedback.

---

