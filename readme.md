<div align="center">

# 🌌 Galaxy Generator

**A procedurally generated, fully customizable spiral galaxy of thousands of particles, rendered in real time with Three.js.**

[![Three.js](https://img.shields.io/badge/Three.js-000000?logo=three.js&logoColor=white)](https://threejs.org)
[![Vite](https://img.shields.io/badge/Vite-646CFF?logo=vite&logoColor=white)](https://vitejs.dev)
[![lil-gui](https://img.shields.io/badge/lil--gui-debug%20UI-blue)](https://lil-gui.georgealways.com/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)

</div>

## Overview

A GPU-friendly particle system that builds a spiral galaxy from scratch using Three.js's `BufferGeometry` and `Points`. Every star's position, color, and distance from the center is calculated procedurally — spun into spiral arms, colored with a gradient from core to edge, and randomized just enough to feel organic rather than mathematically perfect.

A `lil-gui` debug panel exposes every parameter of the generator live, so you can reshape the entire galaxy — star count, radius, branch count, spin, randomness, and color — without touching code.

## ✨ Features

- **Fully procedural galaxy** — thousands of particles positioned via polar coordinates and spiral-arm math, regenerated instantly on parameter change
- **Live-tunable parameters** — star count, radius, branch count, spin strength, randomness/randomness power, and inner/outer color, all controllable via GUI
- **Smooth color gradients** — per-particle color interpolated between a core color and an outer-edge color based on distance from center
- **Efficient rendering** — a single `BufferGeometry` + `Points` object handles all particles in one draw call, keeping frame rates high even with large star counts
- **Clean regeneration** — old geometry, material, and points are properly disposed of before rebuilding, avoiding memory leaks when parameters change

## 🧱 Tech Stack

| Layer | Choice |
|---|---|
| 3D rendering | [Three.js](https://threejs.org) |
| Build tool | [Vite](https://vitejs.dev) |
| Debug UI | [lil-gui](https://lil-gui.georgealways.com/) |
| Language | Vanilla JavaScript (ES modules) |

## 🚀 Getting Started

### Prerequisites

- [Node.js](https://nodejs.org/en/download/) (LTS recommended)

### Installation

```bash
git clone https://github.com/Tensae-abita/18-galaxy-generator.git
cd 18-galaxy-generator
npm install
```

### Run locally

```bash
npm run dev
```

Vite will print a local URL in your terminal (typically `http://localhost:5173`) — open it in your browser to view the galaxy.

### Build for production

```bash
npm run build
```

Outputs an optimized, static build to the `dist/` directory, ready to deploy anywhere that serves static files (Netlify, Vercel, GitHub Pages, etc.).

## 📁 Project Structure

```
src/
├── script.js        # Scene setup, galaxy generation logic, GUI bindings, animation loop
└── style.css         # Base page styling

static/                # Static assets (if any textures/fonts are used)
```

## 🎨 Tuning the Galaxy

Open the `lil-gui` panel in the corner of the page to adjust parameters live:

| Parameter | Effect |
|---|---|
| Count | Total number of particles/stars |
| Radius | Overall size of the galaxy |
| Branches | Number of spiral arms |
| Spin | How tightly the arms curl |
| Randomness | Scatter applied to each star's position |
| Randomness Power | Concentrates randomness toward the center vs. edges |
| Inside Color / Outside Color | Gradient endpoints for star coloring |

For structural changes beyond what the GUI exposes, edit the generation function in `src/script.js` directly.

## 📄 License

This project is licensed under the MIT License — see the [LICENSE](./LICENSE) file for details.
