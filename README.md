## Static GLib 2.0 libraries for building R package RcppCWB on macOS

This repository is modelled after the [rwinlib](https://github.com/rwinlib) family of packages for building R packages on Windows. It offers the (static) [GLib 2.0](https://lazka.github.io/pgi-docs/GLib-2.0) library that is necessary for building the [RcppCWB](https://github.com/PolMine/RcppCWB/) package on macOS.

For macOS users, offering the libraries here is a matter of convenience. It is easy to install  GLib 2.0 using Homebrew (`brew install glib`). The mechanism of the configure script of RcppCWB ensures that the libraries are loaded from this repository if not. 

The most important reason to host GLib 2.0 here is that the library is not available on CRAN build machines. The ability to download the library from this repo ensures that RcppCWB can be build on CRAN macOS build machines and that macOS binaries are available for macOS via CRAN.

## What's in this repository

The static libraries in this repository are the ones that are installed when installing GLib using Homebrew. Note that the repository includes compiled static libraries both for the x86_64 architecture and the M1 chip (files directories lib/x86_64 and lib/arm64 respectively). Files not in these subdirectories are kept there for reasons of backward compatiblity, when the M1 chip was not yet around.

Apart from this, the directory structure corresponds to what is created with a Homebrew installation. The pkgconfig file is identical with the one installed using Homebrew.

## Acknowledgements

The work of everybody behind GLib (the [GTK+-Team](https://www.gtk.org/docs/#team) in particular) is gratefully acknowledged. We greatly appreciate the work of the team offering Homebrew - compiling GLib is notoriously difficult and we took the liberty to build on the work of Homebrew.