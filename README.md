# gitprompt-rs

A very simple Git prompt written in Rust

## Usage

Just add `$(gitprompt-rs)` to your shell prompt. Make sure you use single quotes
`'` or escape the `$` to prevent early expansion.  
Zsh additionally requires `setopt promptsubst` to make this work.

You most likely want to let your shell know that the color escape sequences are
not actually visible so it will calculate the length correctly. Pass `bash` for
Bash or `zsh` for Zsh.

The prompt looks like this: `(master↑4↓7|+2~3-5x6•8)`. The information on
display is as follows:
- Branch info:
  - `master`: name of the current branch, `:HEAD` in detached head mode
  - `↑`: number of commits ahead of remote
  - `↓`: number of commits behind remote
- Work area:
  - `+`: untracked (new) files
  - `~`: modified files
  - `-`: deleted files
  - `x`: merge conflicts
- `•`: staged changes

## Installation

- Manual: Make sure you have a recent Rust toolchain. Clone this repo, then run
  `cargo install --path .`.
- [crates.io](https://crates.io/crates/gitprompt-rs):
  `cargo install gitprompt-rs`
- [Arch Linux](https://www.archlinux.org/packages?name=gitprompt-rs):
  `pacman -S gitprompt-rs`
- Other distros: make a pull request to add your package or build script!
