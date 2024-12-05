# Per-application display scaling on Linux using the Sway WM instances

A demonstration of a bit hacky, but simple method for getting **per-application GUI scaling** on Linux desktop.

Purpose of this is to better display the user interfaces of older applications, which do not normally scale to modern OS GUI resolutions and therefore appear tiny.

It is done by containing the application in a window of a [Sway window manager](https://swaywm.org/) instance, with a custom display scale applied.

**Running Sway as the host graphical environment is not required.** Sway can be launched in a window under X11 and Wayland. This is why I think this solution should work OK in most Linux GUI environments.

This repository is not a library, so just copy and modify these files to suit your needs.

## Usage

To launch application `ddd` at the display scale multiplied by `1.35`:

```sh
swayscale "1.25" "ddd"
```

## Desktop files

To launch the upscaled application from the application launcher of a Linux desktop environment, a Desktop file can be created in `${XDG_DATA_HOME:-$HOME/.local/share}/applications/` directory.

See the example [`ddd_upscaled.desktop`](./.local/share/applications/ddd_upscaled.desktop) file.

Related specifications: ["Desktop Entry Specification"](https://specifications.freedesktop.org/desktop-entry-spec/latest/), ["Association between MIME types and applications"](https://specifications.freedesktop.org/mime-apps-spec/latest/).

## Requirements

`sway` and `awk`.
