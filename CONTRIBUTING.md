# Contributing

Contributions are welcome, especially:

- simulation parameter documentation,
- reproducibility fixes,
- Rust/Bevy maintenance,
- CI improvements,
- paper-to-code mapping notes,
- examples of new restriction masks.

## Pull Requests

Keep changes focused and explain whether they alter simulation behavior, rendering, assets, or documentation.

Before opening a pull request, run these checks if Rust is available locally:

```bash
cargo fmt --check
cargo clippy --all-targets --all-features
cargo test --all-features
```

## Data and Assets

Do not add private experimental videos, unpublished research materials, or large generated outputs without discussing the scope first.
