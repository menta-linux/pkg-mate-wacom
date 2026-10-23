# mate-wacom Debian packaging

This repository creates source and binary Debian packages for
[mate-wacom](https://github.com/KeremSoke/mate-wacom), then attaches them to
archived GitHub Releases. See [CHANNELS.md](CHANNELS.md) for channel and version
rules.

The built package installs `mate-wacom-properties`, its MATE desktop entry and
translations. It depends on `xserver-xorg-input-wacom` for `xsetwacom` and on
`x11-xserver-utils` for `xrandr`; the utility requires an X11 session.
