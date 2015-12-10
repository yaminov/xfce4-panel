# xfce4-panel
from http://git.xfce.org/xfce/xfce4-panel

## Purpose

This fork intended to fix the bug with xfce4-panel behavior when panel is used in dual monitor configuration (panel overlaps application maximized windows). The bug is described in details here: https://bugzilla.xfce.org/show_bug.cgi?id=10957

## Build Guide

### Install dependencies
`sudo apt-get build-dep xfce4-panel`

### Configure
`./autogen.sh --prefix=/usr --libdir=/usr/lib/x86_64-linux-gnu`

### Build
`make`

### Install
`sudo make install`
