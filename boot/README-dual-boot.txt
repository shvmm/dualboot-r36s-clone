Dual boot on a new dArkOS4Clone card (R36S clone, clone type 2, panel 1)
=======================================================================

Before you start: set the card up for dArkOS the normal way (its console
selection for "clone type2 panel1") and let dArkOS finish its first boot,
including any automatic reboots. Its BOOT partition then has, among
others, boot.ini, Image, uInitrd and rk3326-r36s-type2-panel1-linux.dtb.

1. On the BOOT partition, rename boot.ini to boot.ini.darkos.
2. Copy the five files below onto the BOOT partition:
     boot.ini                 boot menu
     boot.ini.mainline        starts mainline directly (no menu)
     Image-mainline           Linux 7.3.4 kernel
     mainline-r36s-clone.fdt  its device tree
     r36s-hwtest.uInitrd      the test tool (whole mainline userland)
   Change nothing else; the menu uses dArkOS's own Image, uInitrd and
   rk3326-r36s-type2-panel1-linux.dtb.
3. Eject safely, put the card in the console, switch on.

Menu: 4 s countdown to Mainline; any key stops it. VOL+/VOL- or D-pad
up/down move, POWER or A starts. To make dArkOS the default, set
menu_default to "darkos" at the top of boot.ini.

dArkOS updates may replace boot.ini (its own header says so). Then the
console simply starts dArkOS directly: rename that new boot.ini to
boot.ini.darkos and copy the menu's boot.ini back.

Back to dArkOS only: delete boot.ini, rename boot.ini.darkos to boot.ini.
Mainline only: delete boot.ini, rename boot.ini.mainline to boot.ini.
