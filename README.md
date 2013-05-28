treecat
=======

list directory tree and content or type of files

usage
-----

    treecat [options] <directory>

options
-------

    -h       print usage and options
    -i <n>   directory depth indentation
    -l <n>   print max <n> lines of a file
    -p       do not print parent path at top

example
-------

    ❱❱ treecat -l3 /etc/X11/
    [/etc/]
    X11/
      xinit/
        xinitrc.d/
          30-dbus
          | #!/bin/bash
          | 
          | # launches a session dbus instance
          | ...
          `-----------------------------------
          40-libcanberra-gtk-module
          | #!/bin/bash
          | 
          | case "$DESKTOP_SESSION" in
          | ...
          `---------------------------
          pulseaudio
          | #!/bin/bash
          | 
          | case "$DESKTOP_SESSION" in
          | ...
          `---------------------------
          xdg-user-dirs
          | #!/bin/sh
          | 
          | # Set up user directories like ~/Desktop and ~/Music
          | ...
          `-----------------------------------------------------
      xorg.conf.d/
        10-evdev.conf
        | #
        | # Catch-all evdev loader for udev-based systems
        | # We don't simply match on any device since that also adds accelerometers
        | ...
        `--------------------------------------------------------------------------
        10-quirks.conf
        | # Collection of quirks and blacklist/whitelists for specific devices.
        | 
        | 
        | ...
        `----------------------------------------------------------------------
        30-mydefaults.conf
        | Section "InputClass"
        |   Identifier      "My Keyboard"
        |   MatchIsKeyboard "yes"
        | ...
        `--------------------------------

