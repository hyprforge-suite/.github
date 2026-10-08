# Contributing to Hyprforge

Thanks for looking. Two things are worth knowing before you open a pull
request.

## Where a change goes

Each component repository (`hyprforge-files`, `hyprforge-lock`, and so on)
is the real home of its code. The suite repository,
[hyprforge-suite/hyprforge](https://github.com/hyprforge-suite/hyprforge),
holds the shared libraries and includes each component as a git submodule at
`crates/<component>`.

- **A change inside one component** — the greeter, say — is a pull request
  against that component's repository. There is no second copy for it to be
  carried back into; the suite picks it up when its submodule pin moves.
- **A change that touches a shared library** (anything under `crates/` that
  is not itself a component) goes to the suite repository. That is the point
  of the suite: a shared fix is one change in one place.
- **A change that crosses the boundary** — a library and a component that
  uses it — lands in order: the library in the suite repository, a release
  to crates.io, then the component. Open the suite pull request first and
  say in it which component change depends on it.

If you are unsure, open an issue on the suite repository and ask.

## Building one component alone

Clone the component's repository and `cargo build`. Its Hyprforge
dependencies are published versions from crates.io, fetched by Cargo; you do
not need to clone the suite. To work on the suite and its components
together, clone the suite with `git clone --recurse-submodules`. Native libraries a build needs are listed in that
repository's `.github/workflows/ci.yml`.

## Before you push

The suite's `./check.sh --quick` (clippy silent, every test green) is what
its pre-commit hook runs; a component's own CI runs the equivalent for that
crate. `CLAUDE.md` in the suite repository is the working conventions of the
project — comments explain *why*, tests are named as the property they pin —
and reads well as a contributor guide too.
