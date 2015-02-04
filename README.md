Introduction
============

The gousb package is an attempt at wrapping the libusb library into a Go-like binding.

Supported platforms include:

- linux
- darwin
- openbsd (no hotplug)

Windows support is unconfirmed, but should work via cgo and [libusb-win32](http://sourceforge.net/apps/trac/libusb-win32/wiki).

Installation
============

Dependencies
------------
You must first install [libusb-1.0](http://libusb.org/wiki/libusb-1.0). On
Darwin/OS X only `brew install libusb` is tested.

Example: lsusb
--------------
The gousb project provides a simple but useful example: lsusb.  This binary
will list the USB devices connected to your system and various interesting
tidbits about them, their configurations, endpoints, etc.  To install it, run
the following command:

    go get -v github.com/kylelemons/gousb/lsusb

gousb
-----
If you installed the lsusb example, both libraries below are already installed.

Installing the primary gousb package is really easy:

    go get -v github.com/kylelemons/gousb/usb

There is also a `usbid` package that will not be installed by default by this
command, but which provides useful information including the human-readable
vendor and product codes for detected hardware.  It's not installed by default
and not linked into the `usb` package by default because it adds ~400kb to the
resulting binary.  If you want both, they can be installed thus:

    go get -v github.com/kylelemons/gousb/usb{,id}

Documentation
=============
The documentation can be viewed via local godoc or via Gary Burd's excellent [godoc.org](http://godoc.org/):

- [usb](http://godoc.org/github.com/kylelemons/gousb/usb)
- [usbid](http://godoc.org/pkg/github.com/kylelemons/gousb/usbid)
