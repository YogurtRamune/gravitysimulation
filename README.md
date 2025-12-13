# Gravity Simulation Website V2.6

This is a web-based gravity simulation tool that allows users to create and simulate particles under gravitational forces. Built with HTML, CSS, and JavaScript, it provides an interactive canvas for visualizing particle interactions, with features like customizable settings, particle generation, templates, and real-time controls.

Live Demo: [https://yogurtramune.github.io/gravitysimulation/](https://yogurtramune.github.io/gravitysimulation/)

## Features

- **Particle Generation**: Create particles with custom mass, size, color, initial velocity, and position. Generate randomly scattered particles or at specific coordinates.
- **Simulation Controls**: Play, pause, and end simulations. Real-time gravitational calculations based on Newton's law of universal gravitation.
- **Zoom and Drag**: Pan and zoom the canvas for better viewing of large-scale simulations.
- **Settings Customization**: Adjust gravitational constant (G), acceleration limits, minimum distances, timesteps, and distance scaling.
- **Particle List**: View and manage individual particles, including real-time attributes like position, velocity, and acceleration.
- **Templates**: Save, load, export, and import simulation setups as JSON for quick reuse (e.g., solar system model).
- **Responsive Design**: Works on desktop and mobile devices, with touch support for dragging and pinching to zoom.
- **Performance Optimizations**: Pauses simulation when the tab is inactive to save resources.

## Getting Started

### Running Locally

1. Clone the repository:
   ```
   git clone https://github.com/yogurtramune/gravitysimulation.git
   ```
2. Open `index.html` in your web browser (e.g., Chrome, Firefox).
   
   No server is required as it's a static site, but you can use a local server like Live Server in VS Code for a better development experience.

### Accessing Online

Visit the live demo: [https://yogurtramune.github.io/gravitysimulation/](https://yogurtramune.github.io/gravitysimulation/)

## How to Use

The interface consists of a canvas for the simulation and a bottom menu bar with icons. Hover over icons for tooltips (on desktop). On mobile, tap icons to interact.

### Menu Icons (from left to right)

- **Settings** (gear icon): Opens the settings popup.
- **Particle List** (particles icon): View and manage all particles.
- **Insert Particles** (insert icon): Generate new particles.
- **Play/Start** (play icon): Starts or resumes the simulation.
- **Pause** (pause icon): Pauses the simulation (replaces play icon when active).
- **End** (stop icon): Stops the simulation and clears all particles.
- **Drag Mode** (drag icon): Toggle drag mode for panning the canvas. When enabled, click/tap and drag to move the view.
- **Zoom** (magnifier icon): Enter a percentage (e.g., 100%) to zoom the canvas. Use mouse wheel (desktop) or pinch (mobile) for dynamic zooming when drag mode is on.

### Generating Particles

1. Click the **Insert Particles** icon to open the generator popup.
2. Set parameters:
   - **Particles Amount**: Number of particles to generate (for random scattering).
   - **Mass**: Particle mass (affects gravity; default: 1).
   - **Size**: Visual size on canvas (default: 1 pixel).
   - **Color**: Hex color (default: #ffffff).
   - **Initial Velocity X/Y**: Starting speed in meters (default: 0).
3. Options:
   - **Generate Scattered All Over Screen**: Randomly places particles across the visible canvas.
   - **Desired Position Generate**:
     - Set **ID Name** (optional, for identification).
     - Set **X/Y Position** (coordinates in simulation space).
     - Enable **Generate on Touch/Click** to add particles by clicking/tapping the canvas.
     - Click **Generate** to add.
4. Close the popup with **Go Back**.

Particles appear as colored squares on the canvas. Gravity starts affecting them when the simulation is running.

### Running the Simulation

- Click **Play** to start. Particles will attract each other based on mass and distance.
- Use **Pause** to freeze the simulation (particles stop moving but remain visible).
- **End** clears everything and resets.

### Viewing and Managing Particles

1. Click the **Particle List** icon.
2. Expand particles by clicking their ID (▶ icon) to view attributes:
   - Position (x, y)
   - Mass, Size, Color
   - Velocity (vx, vy)
   - Acceleration (ax, ay) – updates in real-time during simulation.
3. **Delete** a particle or use **Remove All Particles** to clear the list.
4. Access **Templates** from here (see below).

### Adjusting Settings

1. Click the **Settings** icon.
2. Modify values:
   - **G Constant**: Gravitational constant (default: 6.6743e-11).
   - **Acceleration Limit (m)**: Caps max acceleration to prevent instability.
   - **Interstice Distant Minimum (m)**: Minimum distance to avoid division by zero.
   - **Timestep (hr:sec)**: Simulation speed (e.g., 0.0002777777 hours : 1 second).
   - **Distant Multiplier (mil km:px)**: Scales distances (e.g., 0.000000001 mil km : 1 pixel).
   - **Use Math.ceil() when render**: For pixel-perfect rendering (checkbox).
3. Click **Apply** to save changes. These affect physics calculations instantly.

### Using Templates

1. From the Particle List popup, click **Templates**.
2. **Save New Template**:
   - Enter a name (default: "Untitled").
   - Click **Save** to store locally (via browser storage).
   - Or **Export as JSON** to download/share.
3. **Load Templates**:
   - Default templates (e.g., "Solar System") are pre-loaded.
   - User-saved templates appear below.
   - Click **Load** to add particles to the current simulation.
   - **Export as JSON** or **Delete** for saved templates.
4. **Import Template**:
   - Click **Load Template from JSON**.
   - Paste JSON into the textarea.
   - Click **Confirm Import** to add.

Example Solar System Template:
- Sun at center with planets (Mercury to Neptune) orbiting with realistic masses and velocities.

### Controls and Interactions

- **Desktop**:
  - Mouse drag (with drag mode on) to pan.
  - Mouse wheel to zoom (drag mode on).
  - Click to add particles if "Generate on Touch/Click" is enabled.
- **Mobile**:
  - Tap and drag to pan (drag mode on).
  - Pinch to zoom.
  - Tap to add particles if enabled.
- Simulation pauses automatically when the tab is inactive.

## Tips and Notes

- High particle counts or small timesteps may impact performance.
- Distances are in a scaled simulation space (adjust via settings for realism).
- Zero-mass particles don't attract others but can be affected.
- Binary files (e.g., SVGs, favicons) are not editable here; refer to the repo for assets.
- For development: Edit `script.js` for logic, `style.css` for styling.

## Changelog

<details>
  <summary>View Changelog</summary>

- **V2.6**:
  - Added `user-scalable=no` in viewport meta tag for better mobile experience.

- **V2.5**:
  - Replaced zoom function with more accurate calculations.
  - Fixed null particle names in exports.
  - Removed reset velocity feature.

- **V2.4**:
  - Added template system.
  - Reworked particle system.
  - Added wheel and pinch zoom.
  - Fixed pause button alignment in WebKit.
  - Fixed generate bug when zoomed.
  - Fixed gravitational formula.

- **V2.3.2**:
  - Implemented dragging on touch devices.

- **V2.3.1**:
  - Fixed untappable bug on touch devices.

- **V2.3**:
  - Fixed UI for touch devices (better responsiveness).

- **V2.2**:
  - Generate on click/touch with position/ID.
  - New zoom and drag system.
  - Random generation respects zoom/drag.
  - Fixed zero-mass acceleration bug.

- **V2.1**:
  - Desired position and ID for particles.
  - Canceled selection features.
  - Pause on inactive tab.
  - Fixed distance ratio issues.

</details>

## License

Copyright © YogurtRamune 2025. All rights reserved.

This project is not open-source for commercial use without permission. See the code for details.

