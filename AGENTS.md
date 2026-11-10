# Agent guide

This repository is the owner's hand-written Lean code and notes for reading
*Types and Programming Languages* (Benjamin C. Pierce). See `README.md` for the
layout.

## Environment

- Run every `lean`/`lake` command inside the devShell: either the shell is
  already loaded by direnv, or prefix the command with `nix develop -c`.
- The devShell only provides `elan`. The toolchain comes from `lean-toolchain`
  and is downloaded by elan on demand.
- Do not add Lean toolchains or other packages to `flake.nix`; the toolchain
  belongs in `lean-toolchain`.

## Layout

- `Tapl/ChNN.lean` — the owner's code for chapter NN, in namespace `Tapl.ChNN`.
- `notes/chNN.md` — the owner's notes for chapter NN.
- `Tapl.lean` — library root; imports every chapter.

## Building

```sh
nix develop -c lake build
```

## Conventions

- The chapter files are the owner's to write. Do not fill in definitions,
  proofs or exercise solutions unless asked.
- Do not change `lean-toolchain` unless asked; bumping it can break the
  owner's existing code.
- Learning notes may be in any language; everything else (READMEs, this file,
  commits, PRs) is in English.
