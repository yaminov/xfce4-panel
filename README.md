# xfce4-panel
from http://git.xfce.org/xfce/xfce4-panel

## Purpose

This fork intended to fix the bug with xfce4-panel behavior when panel is used in dual monitor configuration (panel overlaps application maximized windows). The bug is described in details: https://forum.xfce.org/viewtopic.php?id=8802 and https://bugzilla.xfce.org/show_bug.cgi?id=10957

## Build Guide (for amd64)

### Install dependencies
`sudo apt-get build-dep xfce4-panel`

### Get sources
`git clone https://github.com/yaminov/xfce4-panel.git`
`git checkout yaminov/struts`

### Configure
`./autogen.sh --prefix=/usr --libdir=/usr/lib/x86_64-linux-gnu`

### Build
`make`

### Install
`sudo make install`

## Run

After installation panel could be restarter by command
`xfce4-panel -r`

If builded panel doesn't work properly probably unchecking of "Span monitors" checkbox in Xfce Panel preferences dialog could help

## Old plugins compatibility

In amd64 architecture systems plugins are located at the next places:

    /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins
    /usr/lib/x86_64-linux-gnu/xfce4/panel-plugins

Panel looks these locations for plugin binaries. But some plugins could store binaries at /usr/lib/xfce4/panel/plugins and /usr/lib/xfce4/panel-plugins, so they cannot be found by panel.
The problem can be solved by creating symlinks in proper directory. Here is example for dockbarx plugin:

   `sudo ln -s /usr/lib/xfce4/panel/plugins/libdockbarx.so /usr/lib/x86_64-linux-gnu/xfce4/panel/plugins/libdockbarx.so`
