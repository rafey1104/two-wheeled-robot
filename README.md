# Vehicle Simulation in Gazebo

This repository contains an SDF (Simulation Description Format) file that sets up a simple Gazebo simulation environment. The environment features a vehicle with a differential drive system and custom keypress-triggered motion. The simulation includes essential physics plugins, a ground plane, and lighting to create a realistic simulation experience.

---

## Features

### 1. Vehicle Model
- **Chassis**:
  - A box-shaped chassis with dimensions `2.0 x 1.0 x 0.5`.
  - Colored **blue** for easy identification.
- **Wheels**:
  - Two revolute (rotational) wheels on the left and right, colored **red**.
  - One caster wheel (ball joint) at the front, represented as a **green sphere**.

### 2. Plugins
- **Physics System**: Handles the physics simulation in Gazebo.
- **User Commands System**: Allows interaction with the simulation via commands.
- **Scene Broadcaster System**: Broadcasts the state of the simulation for visualization purposes.
- **Differential Drive System**:
  - Drives the left and right wheels using input commands.
  - Publishes odometry data.
  - Configured for:
    - **Wheel separation**: `1.2`
    - **Wheel radius**: `0.4`.

### 3. Keyboard Controls
The vehicle's motion is controlled by keypresses, which are mapped to specific `cmd_vel` (velocity command) topics:

| **Action**       | **Keycode** | **Linear Velocity (m/s)** | **Angular Velocity (rad/s)** |
|-------------------|-------------|---------------------------|------------------------------|
| **Forward**       | `16777235`  | `0.5`                     | `0.0`                        |
| **Backward**      | `16777237`  | `-0.5`                    | `0.0`                        |
| **Rotate Left**   | `16777234`  | `0.0`                     | `0.5`                        |
| **Rotate Right**  | `16777236`  | `0.0`                     | `-0.5`                       |

### 4. Environment
- **Ground Plane**:
  - A static, infinite ground with a neutral **gray** color.
- **Lighting**:
  - A directional light (**sun**) simulates natural sunlight, including shadows for added realism.
