# FungiLifeGame

[中文](README.zh-CN.md) | English

[![Rust](https://img.shields.io/badge/Rust-2021-000000?logo=rust)](Cargo.toml)
[![Bevy](https://img.shields.io/badge/Bevy-0.13-232326)](https://bevyengine.org/)
[![Paper](https://img.shields.io/badge/Paper-SIGGRAPH%20Asia%202024-8A2BE2)](https://doi.org/10.1145/3680530.3695440)
[![arXiv](https://img.shields.io/badge/arXiv-2409.05171-b31b1b)](https://arxiv.org/abs/2409.05171)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

A Bevy/Rust cellular-automata simulation for fungal morphology exploration and light-boundary containment, associated with the SIGGRAPH Asia 2024 Art Papers work **Exploring Fungal Morphology Simulation and Dynamic Light Containment from a Graphics Generation Perspective**.

![Fungal simulation and light containment](docs/assets/fungal-simulation-figure1.png)

The figure above is cropped from the paper PDF for repository presentation.

## What It Does

FungiLifeGame simulates fungal spread on a 2D grid with local growth, resource consumption, restrictions, and light-like boundary feedback. It is a compact interactive prototype for exploring how fungal growth can be represented as a graphic time-series system.

The broader paper couples learned fungal spread dynamics with real-world light containment. This repository contains the Rust/Bevy simulation side: grid state, growth rules, visual feedback, and restriction-mask driven morphology.

## Quick Start

```bash
git clone https://github.com/sunyitong/FungiLifeGame.git
cd FungiLifeGame
cargo run --release
```

The app opens a square Bevy window and starts the growth simulation from the configured initial position.

## Controls

The current prototype runs automatically. Configuration is edited in [`src/init_data.rs`](src/init_data.rs):

| Constant | Meaning |
| --- | --- |
| `CANVAS_SIZE` | Simulation grid size and window resolution. |
| `RESTRICTION_IMAGE` | Image mask used to define growth boundaries. |
| `FUNGI_INIT_POSITION` | Initial spawn point. |
| `FUNGI_STEP_DISTANCE` | Maximum local growth step. |
| `LIGHT_LIFE_TIME` | Duration of light feedback spawned at restricted boundaries. |
| `*_COLOR` | Visual palette for living, dead, newborn, restricted, and light states. |

## Repository Layout

```text
src/
  main.rs          Bevy app setup
  components.rs    ECS components and resources
  systems.rs       growth, spawning, restriction, and light systems
  init_data.rs     simulation constants
assets/images/     masks and visual assets
docs/assets/       README and paper-derived presentation images
```

## Paper

- DOI: <https://doi.org/10.1145/3680530.3695440>
- arXiv: <https://arxiv.org/abs/2409.05171>
- Project page: <https://yitongsun.com/fungal-simulation>

## Citation

If you use this repository or build on the simulation, please cite:

```bibtex
@inproceedings{Wang_2024,
  title={Exploring Fungal Morphology Simulation and Dynamic Light Containment from a Graphics Generation Perspective},
  DOI={10.1145/3680530.3695440},
  booktitle={SIGGRAPH Asia 2024 Art Papers},
  publisher={ACM},
  author={Wang, Kexin and He, Ivy and Li, Jinke and Asadipour, Ali and Sun, Yitong},
  year={2024},
  pages={1--8}
}
```

## Development

```bash
cargo fmt
cargo clippy --all-targets --all-features
cargo test
```

## License

This repository is released under the [MIT License](LICENSE).
