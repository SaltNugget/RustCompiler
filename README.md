# RustCompiler

Quick Rust compile tool. Point it at a `.rs` file or a folder and it builds for you. 

I made this cuz im learning rust and I hate the compile process so why not make it auto

## Requirements

- Python 3
- Rust toolchain (`rustc` and `cargo`), install via https://rustup.rs

## Usage

```bash
python rc.py                  # prompts for a path
python rc.py hello.rs         # compile one file
python rc.py ./myfolder       # compile a folder
```

On Linux you can also run it directly:

```bash
chmod +x rc.py
./rc.py hello.rs
```

## What it does

| Input | Action |
|---|---|
| `.rs` file | Compiles it with `rustc` to an exe of the same name |
| Folder with `Cargo.toml` | Runs `cargo build --release` |
| Folder without `Cargo.toml` | Compiles each `.rs` file on its own and prints `X ok, Y failed` |
| Bad path | Says so and reprompts (prompt mode only) |

- Output is `name.exe` on Windows and `name` on Linux, next to the source file.
- Ctrl+C stops cleanly, deletes the half-built exe, and shows how many files finished.
- If you pass a path as an argument, it runs once and exits without prompting.
