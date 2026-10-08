# Hyprforge

A suite of native desktop applications for [Hyprland](https://hyprland.org):
one shared look, one keyboard grammar, one place to fix a shared thing —
and every component installable on its own.

| Repository | What it is |
|---|---|
| [hyprforge](https://github.com/hyprforge-suite/hyprforge) | The suite: every shared library, the packaging, the checks, and where development happens. **Start here.** |
| [hyprforge-settings](https://github.com/hyprforge-suite/hyprforge-settings) | The Settings app |
| [hyprforge-files](https://github.com/hyprforge-suite/hyprforge-files) | The file manager |
| [hyprforge-media](https://github.com/hyprforge-suite/hyprforge-media) | The photo, video and 3D model viewer |
| [hyprforge-lock](https://github.com/hyprforge-suite/hyprforge-lock) | The lock screen |
| [hyprforge-greet](https://github.com/hyprforge-suite/hyprforge-greet) | The greetd greeter |
| [hyprforge-displayd](https://github.com/hyprforge-suite/hyprforge-displayd) | The monitor-layout daemon |
| [hyprforge-tray](https://github.com/hyprforge-suite/hyprforge-tray) | The tray daemon and its menu |
| [hyprforge-clipboard](https://github.com/hyprforge-suite/hyprforge-clipboard) | Clipboard history and its popup |
| [hyprforge-emojimenu](https://github.com/hyprforge-suite/hyprforge-emojimenu) | The emoji picker |
| [hyprforge-notif](https://github.com/hyprforge-suite/hyprforge-notif) | The notification daemon and its notification center |

Each component repository is the real home of its code, and the suite
repository includes it as a git submodule at `crates/<component>`. The shared
libraries live in the suite repository and are published to
[crates.io](https://crates.io/search?q=hyprforge), which is where a component
built on its own gets them. The suite's README explains the layout and how the
pieces fit; see
[CONTRIBUTING](https://github.com/hyprforge-suite/.github/blob/main/CONTRIBUTING.md)
for where to send a change.
