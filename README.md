# treecat
List directory tree with file mime-type and content.

## Usage
```
treecat [options] <directory>
```

## Options
```
-h         print help and options
-c         use colors
-e <expr>  exclude files/dirs          (current: )
-i <n>     indentation width           (current: 4)
-l <n>     lines of a file to print    (current: 0)
-p         parent path printed at top
-r <n>     recursion depth             (current: 0)
-t <n>     tab width (inside files)    (current: 4)
```

## Example
```
❱ ./treecat -p -l 3 /etc/X11/
/etc/X11/
    xinit/
        xinitrc <text/x-shellscript>
        │ #!/bin/sh
        │
        │ userresources=$HOME/.Xresources
        ╵╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶
        xinit/xinitrc.d/
            40-libcanberra-gtk-module.sh <text/x-shellscript>
            │ #!/bin/sh
            │
            │ case "${DESKTOP_SESSION-}" in
            ╵╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶
            50-systemd-user.sh <text/x-shellscript>
            │ #!/bin/sh
            │
            │ systemctl --user import-environment DISPLAY XAUTHORITY
            ╵╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶
        xserverrc <text/x-shellscript>
        │ #!/bin/sh
        │ exec /usr/bin/X -nolisten tcp "$@"
        ╰───────────────────────────────────
    xorg.conf.d/
        00-keyboard.conf <text/plain>
        │ Section "InputClass"
        │   Identifier      "My Keyboard"
        │   MatchIsKeyboard "yes"
        ╵╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶
        30-mydefaults.conf <text/plain>
        │ Section "InputClass"
        │   Identifier      "My Keyboard"
        │   MatchIsKeyboard "yes"
        ╵╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶╶
```

## Screenshot
![screenshot](screenshot.gif?raw=true "screenshot of treecat color output")
