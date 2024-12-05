# Per-application display scaling on Linux using the Sway WM instances

A demonstration of how to get per-application GUI scaling on Linux, by containing the application in a window of a [Sway window manager](https://swaywm.org/) instance, with a custom display scale applied.

This is intended for user interfaces of those older applications which do not scale to the modern OS GUI font resolution, therefore appear tiny.

This is not a library, so just copy and adapt these files to your needs.

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

## Limitations

All the scaled windows of an application are contained inside of a Sway instance window with the display scale applied.

And so are the other application windows spawned from the application inside the Sway instance window.

## Requirements

`sway` and `awk`.
