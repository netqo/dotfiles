# Dotfiles

Personal [Suckless](https://suckless.org/) desktop environment configuration for Arch Linux, managed with [GNU Stow](https://www.gnu.org/software/stow/). Includes patched builds of dwm, st, dmenu, and slstatus alongside configs for various tools and utilities.

## Repository Structure

```
.
├── .bashrc                 # Shell configuration
├── .config/
│   ├── dunst/              # Notification daemon
│   ├── fastfetch/          # System information tool
│   ├── gtk-3.0/            # GTK3 theme settings
│   ├── gtk-4.0/            # GTK4 theme settings
│   ├── nvim/               # Neovim configuration
│   ├── picom/              # Compositor settings
│   └── ranger/             # Terminal file manager
├── .dwm/                   # dwm autostart scripts
├── .gtkrc-2.0              # GTK2 theme settings
├── .icons/                 # Cursor/icon themes
├── .local/share/icons/     # Additional icon assets
├── .themes/
│   └── Material-Black-Plum-LA/  # GTK theme
├── Photos/                 # Wallpapers
├── scripts/
│   ├── exitdwm.sh          # dwm exit/logout handler
│   ├── logisim             # Logisim launcher
│   ├── minecraft-server-backup.sh
│   └── zenstates.sh        # AMD CPU power management
└── suckless/
    ├── dmenu/              # Application launcher
    ├── dwm/                # Dynamic window manager
    ├── slstatus/           # Status bar
    └── st/                 # Simple terminal
```

## Dependencies

### Required Packages

| Category | Packages |
|---|---|
| Build tools | gcc, git, make, patch, base-devel |
| X11 libraries | libx11, libxft, libxinerama, libxext |
| Font/rendering | freetype2, fontconfig, terminus-font |
| System | coreutils, glibc, ncurses, NetworkManager |
| Desktop | feh, picom, slock, xautolock, wmname, stow |
| Extras | network-manager-applet, syncthing, polkit, lxsession |

### Arch Linux

```bash
pacman -S gcc git make patch polkit lxsession base-devel freetype2 libx11 libxft libxinerama fontconfig coreutils glibc libxext ncurses terminus-font slock xautolock picom stow feh wmname networkmanager network-manager-applet syncthing
```

## Installation

```bash
git clone https://github.com/nullnullnullnullnullnullnullnullnullnul/dotfiles.git ~/dotfiles
cd ~/dotfiles
stow .
```

Build each suckless tool:

```bash
cd ~/dotfiles/suckless/dwm && sudo make clean install
cd ~/dotfiles/suckless/st && sudo make clean install
cd ~/dotfiles/suckless/dmenu && sudo make clean install
cd ~/dotfiles/suckless/slstatus && sudo make clean install
```

## Patches

### dwm

| Patch | Description |
|---|---|
| [autostart](https://dwm.suckless.org/patches/autostart/) | Run commands on dwm startup |
| [statusallmons](https://dwm.suckless.org/patches/statusallmons/) | Show status bar on all monitors |
| [gaps](https://dwm.suckless.org/patches/gaps/) | Gaps between windows |
| [actualfullscreen](https://dwm.suckless.org/patches/actualfullscreen/) | True fullscreen instead of monocle |
| [awesomebarwithhover](https://dwm.suckless.org/patches/awesomebar/) | Clickable window titles in the bar |
| [restartsig](https://dwm.suckless.org/patches/restartsig/) | Restart dwm in place via signal |
| [exitmenu](https://dwm.suckless.org/patches/exitmenu/) | Exit menu with logout/reboot/shutdown |
| [alwayscenter](https://dwm.suckless.org/patches/alwayscenter/) | Floating windows always centered |
| [systray](https://dwm.suckless.org/patches/systray/) | System tray support |
| [fixborders](https://dwm.suckless.org/patches/alpha/) | Fix transparent window borders |

### st

| Patch | Description |
|---|---|
| [anysize](https://st.suckless.org/patches/anysize/) | Remove fixed-size grid restriction |
| [scrollback-ringbuffer](https://st.suckless.org/patches/scrollback/) | Scrollback buffer support |
| [alpha](https://st.suckless.org/patches/alpha/) | Background transparency |
| [blinking-cursor](https://st.suckless.org/patches/blinking_cursor/) | Blinking cursor support |
| [w3m](https://st.suckless.org/patches/w3m/) | Inline image rendering via w3m |

### dmenu

| Patch | Description |
|---|---|
| [case-insensitive](https://tools.suckless.org/dmenu/patches/case-insensitive/) | Case insensitive matching |
| [numbers](https://tools.suckless.org/dmenu/patches/numbers/) | Display number of matched items |

## Color Palette

```
#444444  ██  Dark gray
#bbbbbb  ██  Light gray
#222222  ██  Background
#eeeeee  ██  Foreground
#7a49a5  ██  Accent (purple)
#49A57A  ██  Accent (green)
```
