# Day 1:

## 1.1. Install rustlings

```bash
cargo install --path .
```

`Cargo.toml` : configuration file

Path exporting

```bash
echo 'export PATH="$HOME/.cargo/bin:$PATH"' >> ~/.bashrc
source ~/.bashrc
```

Run

```bash
cargo run
```

## 1.2. What is Rustlings

- Rustlings:
    + Interactive learning application
    + Automatic Watcher & Real-time Feedback
    + Progress Tracking
    + Interactive Menu & Helper Commands:
        * `rustlings hint`
        * `rustlings reset`

## 1.3. Rust Ecosystem

1. rustup       toolchain manager
                install and updates rustc, cargo
                every 6 weeks: rustup update
                uninstall: rustup self uninstall
2. cargo        package & build manager
3. rustc        compiler
4. rustlings    learning app

## 2. Project with Cargo

- cargo new:

```bash
cargo new hello_cargo 
cd hello_cargo
```
It has also initialized a new Git repository along with a `.gitignore` file. Git files won’t be generated if you run cargo new within an existing Git repository; you can override this behavior by using `cargo new --vcs=git`.

> NOTE: Run `cargo new --help`
> `--vcs <VCS>`
> Initialize a new repository for the given version control system,
> overriding a global configuration. [possible values: git, hg, pijul,
> fossil, none]

After run `cargo new [project_name]`

1. New directory and project called [project_name]
2. Cargo.toml
2. src/ directory, with main.rs

#### Cargo.toml

TOML (Tom's Obvious, Minimal Language) format

- Key parts:
    * Key-Value: `key = "value"`
    * Table: `[section]` group keys together
    * Nested Table: `[section.child]`
    * Array: `list = ["rock", "stick"]`
    * Types: Text, integer, float, boolean, date/time

```toml
[package]
name = "hello_cargo"
version = "0.1.0"
edition = "2024"

[dependencies]
```

Packages of code -> crates

### Recap of Build and Run a Cargo Project

- cargo new:
    * create a project with directory
    * inside has `src/main.rs` and `Cargo.toml`

- cargo build: 
    * creates an executable file in `target/debug/hello_cargo`
    * default build is a debug build
    * `./target/debug/hello_cargo`

- cargo run:
    * more convenient
    * binary executable file in the current path
    * rebuilt (if changed) before running

- cargo check:
    * often faster than cargo build
    * skips producing an executable
    * check code

## 3. Rustc

Compile & Run the generated executable file:

```bash
rustc file.rs
```