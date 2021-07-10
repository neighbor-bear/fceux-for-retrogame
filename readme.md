# FCEUX 2.4.0 for OpenDingux/RetroFW 2

  - Based on soarquin's work and upgraded to upstream 2.4.0 version with
    additions based on gameblabla and pingflood versions.
  - Fixed the exit option from main menu 
  - Load rom: pagination with left and right cursors changed to scroll
    one page
  - For OpenDingux beta: Set video refresh rate based on cartridge region
    (taken from gameblabla's port)
  - Automatically set video mode based on cartridge region
  - Fixed the Flip disc option from main menu
  - Enable Flip disc option in main menu only if a FDS file is inserted
    (taken from pingflood's RetroFW port)
  - Try to load disksys.rom from current rom directory
    (taken from pingflood's RetroFW port)
  - For debug purposes: when launch FCEUX witouth cartridge launch
    emulator rom selector
  - Change button layout in Control Setup
  - Some other minor changes

You can see the upstream FCEUX changelog [here](http://fceux.com/web/help/WhatsNew240.html)

## Compilation

Use `make` to compile. If your toolchain is not in `/opt/gcw0-toolchain` pass your path in the variable **TOOLCHAIN**.

Executable and opk base filenames can be changed with **TARGET** variable. By default the base filename is *fuse_od*. Upstream version and build date will be added to opk name.

To compile for RetroFW pass *retrofw* value to **DEVICE** variable

Examples:

`make TOOLCHAIN=/opt/retrofw2-toolchain TARGET=fceux_retrofw DEVICE=retrofw -f Makefile`

`make TOOLCHAIN=/opt/opendingux-toolchain TARGET=fceux_od_beta -f Makefile`

Build files are created in the `bin`directory.

## Bios file
To load FDS files bios file `disksys.rom` is needed. It must be placed at `$HOME/.fceux` directory or in the game directory.

## Controls

FCEUX|Nes
-|-
Pad|Pad
A|A
B|B
X|TurboA
Y|TurboB
Select|Select
Start|Start
POWER, L2|Open menu

### Hotkeys

Hotkey|Action
-|-
R1 + A				|Save state (current slot from gui is used)
R1 + B 				|Load state (current slot from gui is used)
R1 + X				|Toggle fullscreen
R1 + Y				|Flip fds disk
R1 + UP				|Toggle framerate display
R1 + LEFT			|Insert vsuni coin
R1 + SELECT		|Save snapshot
R1 + START		|Pause emulation
L1					  |Toggle throttling
