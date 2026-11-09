<p align="center">
  <img src="docs/assets/khe-whale-v1.png" alt="Khe icon" width="220">
</p>

# Khe

**Khe is a Rust rendering engine for real-world simulation and scientific visualization.**

Khe develops our own Rust rendering engine for real-world simulation: materials, lighting, fluid surfaces, and scientific visualization. Its companion, [Moo](https://github.com/KheMoos/Moo), provides the general physics engine.

## Current state

This is an early rendering prototype using wgpu, with an egui/winit viewer and GPU particle rendering. High-fidelity materials, fluid reconstruction, and physically based reflection/refraction remain roadmap work. Known rendering and simulation defects remain open; extracting this repository does not fix them.

## Build and run

Install a Rust toolchain supporting edition 2024 and use a machine with a compatible graphics backend.

```sh
cargo test --locked
cargo run --locked
```

The `moo` dependency is pinned to a Git revision for reproducibility. No sibling checkout is required. Optional gRPC support is enabled with `--features grpc` and requires `protoc` during the build.

The `index.html` file is the existing WebAssembly viewer shell. Browser support remains experimental and needs separate validation.

## Development

Khe owns rendering and the current interactive viewer. Moo owns physical state, laws, materials, constraints, and solvers. Changes to the boundary between them should include integration validation and an explicit dependency revision update.

## History

This repository was extracted from the `khe/` directory of [Moo](https://github.com/KheMoos/Moo), preserving that directory's Git history. The original shared history and release tags remain in Moo.
