Hootwm - Currently unmaintained & abandoned
=====
My fork of hootwm - A very simple tiling window manager written from scratch using C and xcb, inspired by catwm.

lswm ignores all keyboard events, but it can be controlled by sending commands to the named pipe located in `/tmp/hootwm` by default.
A grabbing keys utility such as `xbindkeys` or `sxhkd` may be used to implement hotkeys.

## Commands
| Command | Arguments | Description |
| ------- | --------- | ----------- |
| `move`  | `up/down` | Move current window up or down |
| `focus` | `up/down` | Shift focus up or down |
| `grow`  | int32_t   | Grow or shrink master area. Positive ints grow, negative ints shrink |
| `switch`| int       | Switch to a different desktop |
| `quit`  | -         | Exit the program cleanly |

Example:
    echo move down > /tmp/hootwm
    echo grow -10 > /tmp/hootwm

Initial gap and border size, master proportion and pipe filename can be defined at compile time by editing `config.h`.
A config file to be evaluated at startup may be added in the future.

## Modes
lswm tiles windows using one master area and a stacking area on the right.

    +--------+---+
    |        |   |
    |        +---+
    | Master |   |
    |        +---+
    |        |   |
    +--------+---+
    Tiled

More modes may be added in the future.

## Installation
 * Install xcb
 * Edit Makefile
 * Compile with `make clean install`
## Bugs
 * When closing a program, it sometimes act as if the program was still there
## Goals
 * Keep it small, keep the code quality and readability good.
## To do
 * Monocle layout?
 * Deck layout?
 * Replace default layout with dwindle?
 * Possibly keybinds
