# dmenu2 - enhanced dynamic menu
[dmenu](https://tools.suckless.org/dmenu/) is an efficient dynamic menu for X. dmenu2 extends upon it to make it easier to use.

![Screenshot](../master/docs/dmenu_both.png)

## Why dmenu2?
Started using dmenu with i3. Most of my menu items were cmdline utilities
invoked through xterm, leading to many "xterm -e ...". Wanted a simple
descriptive label to show up in the dmenu bar instead of the command.
i3-dmenu-desktop accomplishes this by using a perl wrapper around dmenu but it
seemed too heavy weight. Minor enhancements to the dmenu sources and now we have
a nice label. Each item in the menu now has two fields: text and cmd. The text
of the item is displayed and the cmd of the item is printed to stdout if
selected.

## How to use?
Each menu item is seperated by a newline. The cmd and text of an item are seperated by a comma. So `cmd1,text1\n cmd2,text2\n...`.

```bash
echo -e "1,one\n2,two" | dmenu
echo -e "firefox,☎firefox\naterm -e alsamixer,♥alsamixer\nxcalc,☮Calculator\nnvidia-settings,☺nVidia\nzathura,⌘PDF Viewer\nhardinfo,⌨HW Info\naterm -e mocp,♩♪♫mocp♫\naterm -e ranger,☢ranger☢" | dmenu 
```

To use with i3, customize my\_dmenu, and modify i3 config file (~/.config/i3/config). Then `modkey + d`.

```
bindsym $mod+d exec --no-startup-id ~/bin/my\_dmenu
```

## Requirements
To build, you will need X11 development libraries. On Ubuntu Bionic, I had to
install the following: libxcb1-dev, libx11-dev, libxext-dev, libxinerama-dev
and libxft-dev.

