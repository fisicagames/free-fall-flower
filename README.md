# Free Fall Flower 🌻

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![TypeScript](https://img.shields.io/badge/TypeScript-5.7.2-blue.svg)](https://www.typescriptlang.org/)
[![Babylon.js](https://img.shields.io/badge/Babylon.js-7.5.0-purple.svg)](https://www.babylonjs.com/)
[![Vite](https://img.shields.io/badge/Vite-5.2.11-yellow.svg)](https://vitejs.dev/)

The second simulation of the SHIFT series — an interactive simulation on free fall motion.

### [🎮 Play Now!](https://fisicagames.com.br/)

---

## 📄 Table of Contents

* [About the Game](#-about-the-game)
* [Key Features](#-key-features)
* [How to Play](#-how-to-play)
* [Tech Stack](#-tech-stack)
* [Installation and Setup](#-installation-and-setup)
* [Architecture and Technical Highlights](#-architecture-and-technical-highlights)
* [License](#-license)
* [Author](#-author)

---

## 📖 About the Game

**Free Fall Flower** is the second simulation in the SHIFT series, developed in January 2024 as part of the pilot study. Unlike the first simulation, the gameplay mechanic is fully aligned with the hypercasual genre: a flower vase falls from the window of a building, and the player must tap or click anywhere on the screen to stop it before it shatters on the ground.

The closer the vase is to the ground when stopped, the higher the score. The game progresses by adding floors to the building, increasing the fall height and challenging the player's reaction time. The simulation models simplified free fall (without air resistance) and displays the height and elapsed time in real time.

This simulation took only four days to complete, providing valuable timing data for planning the broader serial production of subsequent SHIFT simulations.

---

## ✨ Key Features

* **Single-Tap Hypercasual Gameplay:** Tap anywhere to stop the vase before it hits the ground.
* **Real-Time Equation Display:** The current values of fall height (h) and elapsed time (t) are displayed dynamically in the GUI as the vase falls.
* **Progressive Difficulty:** Each new level adds a floor to the building, increasing the fall height (h₀ = 2.5 × (level + 1) m, starting at 5.0 m).
* **Score Based on Proximity:** Higher scores are awarded for stopping the vase closer to the ground.
* **Fixed Gravity:** g = 9.8 m/s², representing standard Earth gravity at the surface.
* **Responsive:** Runs in any modern browser, optimized for mobile portrait layout.

---

## 🕹 How to Play

**Objective:** Stop the falling vase as close to the ground as possible without letting it shatter.

#### Controls

💻 **On PC:** Click anywhere on the screen.

📱 **On Mobile / Touch:** Tap anywhere on the screen.

---

## 🛠 Tech Stack

| Tool                                       | Version | Description                                                              |
| ------------------------------------------ | ------- | ------------------------------------------------------------------------ |
| [TypeScript](https://www.typescriptlang.org/) | 5.7.2   | Core language, providing type safety.                                    |
| [Babylon.js](https://www.babylonjs.com/)      | 7.5.0   | Graphics engine for 3D rendering and GUI system.                         |
| [Vite.js](https://vitejs.dev/)                | 5.2.11  | Build tool for ES6 module compilation, tree-shaking, and optimization.   |
| [Node.js](https://nodejs.org/en)              | 20+     | Development environment and runtime.                                     |

---

## 🚀 Installation and Setup

**Prerequisites:** Node.js (v20+), npm (v10+).

```sh
npm install
npm run dev      # development server
npm run build    # production build (generates the dist folder)
```

---

## 🏗 Architecture and Technical Highlights

**Free Fall Flower** was developed using the same minimal singleton architecture as the first SHIFT simulation, with all game logic concentrated in a single class. Since the codebase had not yet been modularized, multiple functions had to be modified due to the strong coupling. Game states continued to be managed through a finite state machine.

* **Singleton single-class structure:** Inherits the architecture of the pilot simulation; modularization would only begin in the third simulation of the series.
* **Manual free-fall physics:** The motion is computed without a physics engine, using a discrete approximation of the closed-form equation:

  ```
  h(t) = h₀ − ½ g t²
  ```

  evaluated each frame from accumulated time. The vase's vertical position is updated by subtracting the computed fall distance from the initial height.
* **Real-time on-screen physics:** The GUI displays the current values of t and h on each frame, reinforcing the connection between the quadratic relationship and the observed motion.

This second simulation served as a final technical assessment of the TypeScript + Babylon.js stack before transitioning to the modularization strategy needed for serial production. The four-day development cycle confirmed the viability of the approach and motivated the architectural refactoring that began with the next simulation.

---

## 📸 Screenshots

<!-- Add screenshots here when available, e.g.:
<p align="center">
  <img src="image/README/screenshot1.png" width="30%" alt="Free Fall Flower screenshot 1" />
  <img src="image/README/screenshot2.png" width="30%" alt="Free Fall Flower screenshot 2" />
</p>
-->

---

## 📜 License

### Source Code

The source code in this repository is licensed under the **MIT License** — see the [LICENSE](./LICENSE) file.

### Visual Assets

3D models, textures, and original visual content created by the author are licensed under **Creative Commons Attribution 4.0 International (CC BY 4.0)**.

### Audio Assets

Music and sound effects in this project are sourced from [Pixabay](https://pixabay.com/) under the [Pixabay Content License](https://pixabay.com/service/license-summary/), which permits free use including for commercial purposes.

### Third-Party Libraries

* **Babylon.js** — Apache License 2.0
* **Vite.js** — MIT License

**Copyright © 2024 Rafael João Ribeiro.**

---

## 👨‍🔬 Author

Developed by:
**Prof. Dr. Rafael João Ribeiro**
Federal Institute of Paraná (IFPR)
[www.fisicagames.com.br](https://www.fisicagames.com.br)
