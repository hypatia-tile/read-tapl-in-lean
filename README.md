# read-tapl-in-lean

Reading *Types and Programming Languages* (Benjamin C. Pierce, MIT Press, 2002)
and writing its systems, evaluators and proofs in Lean 4 instead of OCaml.

## Environment

The Nix devShell provides only [elan](https://github.com/leanprover/elan);
`lean` and `lake` are elan proxies that pick the toolchain from
`lean-toolchain` (`v4.35.0`, the latest stable release when this repository
was set up), downloading it into `~/.elan` on first use.

Enter it either way:

- `direnv allow` once — the shell (and any editor started inside the
  repository) then has `elan`, `lean` and `lake` on `PATH`.
- `nix develop` — for a one-off shell, or prefix a command with
  `nix develop -c`.

Build:

```sh
nix develop -c lake build
```

## Layout

```
Tapl.lean          library root; imports each chapter
Tapl/ChNN.lean     code written while reading chapter NN (namespace Tapl.ChNN)
notes/chNN.md      notes for chapter NN
```

Every chapter from 1 to 32 has an empty module and an empty notes file. The
"An ML Implementation of …" chapters (4, 7, 10, 17, 25) are where the book's
OCaml implementations are rewritten in Lean.

Learning notes may be written in any language.
