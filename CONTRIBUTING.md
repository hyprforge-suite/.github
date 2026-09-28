# Contributing to Hyprforge

Thanks for looking. Two things are worth knowing before you open a pull
request.

## Where a change goes

Development happens in the suite repository,
[hyprforge-suite/hyprforge](https://github.com/hyprforge-suite/hyprforge).
Each component repository (`hyprforge-files`, `hyprforge-lock`, and so on)
is a `git subtree` mirror of one directory there, published by the suite's
`sync.sh`.

- **A change inside one component** — the greeter, say — can be opened as a
  pull request against that component's repository. It is pulled back into
  the suite with `git subtree pull`, and the next sync republishes it.
- **A change that touches a shared library** (anything under `crates/` that
  is not itself a component), or that crosses a component boundary, goes to
  the suite repository. That is the point of the suite: a shared fix is one
  change in one place.

If you are unsure, the suite repository is always right.

## Building one component alone

Clone the component's repository and `cargo build`. Its Hyprforge
dependencies are fetched from the suite repository by Cargo; you do not need
to clone the suite. Native libraries a build needs are listed in that
repository's `.github/workflows/ci.yml`.

## Before you push

The suite's `./check.sh --quick` (clippy silent, every test green) is what
its pre-commit hook runs; a component's own CI runs the equivalent for that
crate. `CLAUDE.md` in the suite repository is the working conventions of the
project — comments explain *why*, tests are named as the property they pin —
and reads well as a contributor guide too.
