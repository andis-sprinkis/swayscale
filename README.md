# Per-application display scaling on Linux using the Sway WM instances

A demonstration of a method for getting **per-application GUI scaling** on Linux, by containing the application in a window of a [Sway window manager](https://swaywm.org/) instance, with a custom display scale applied.

It is indented to better display user interfaces of the older applications which do not scale to the modern OS GUI resolutions, therefore appear tiny.

**Running Sway as the host graphical environment is not required for this.** Sway can be launched in a window under X11, so I do assume this solution works in most of the Linux GUI environments.

This repository is not a library, so just copy and adapt these files to your needs.

## Limitations

The scaled windows of a launched application are contained inside a single Sway instance window with the display scale applied. So are the other application windows spawned from the said application.

## Screenshot

## Usage

To launch application `ddd` at the display scale multiplied by `1.35`:

```sh
swayscale "1.35" "ddd"
```

## Desktop files

To launch the upscaled application from the application launcher of a Linux desktop environment, a Desktop file can be created in `${XDG_DATA_HOME:-$HOME/.local/share}/applications/` directory.

See the example [`ddd_upscaled.desktop`](./.local/share/applications/ddd_upscaled.desktop) file.

Related specifications: ["Desktop Entry Specification"](https://specifications.freedesktop.org/desktop-entry-spec/latest/), ["Association between MIME types and applications"](https://specifications.freedesktop.org/mime-apps-spec/latest/).

## Requirements

`sway` and `awk`.
