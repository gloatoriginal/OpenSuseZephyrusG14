# OpenSuseZephyrusG14
Steps in order to get G14 and external displays going on Zephyrus G14, along with Utilities
System: Open Suse Tumbleweed, with 2022 Zephyrus G14 6700s + 6900HS
Reasons: Linux Kernel has built in driver support for AMD GPU with built in MUX switch it should yield good battery life
1) Partition the onboard disk to shrink the Windows volume to allow for 300GB of unused drive space.
2) OpenSuse realized this during installation and selected this disk partition as the default installation
3) Install all Open Source drivers
4) Additional Steps for healthy peripheral integration and battery life:
   - Add Kernel Parameters amd.si_support=1 amd.cik_support=1 radeon.si_support=0 radeon.cik_support=0
   - Install solaar for Logitech Devices, set this as a startup app under "Autostart" in KDE
   - Install TLP for power assistance, set min_charge_threshold=77 and max_charge_threshold=80, disable autosuspend usb
   - Install Powertop, run an initial sudo powertop --calibrate, run sudo powertop --auto-tune, set sudo crontab to /usr/sbin/powertop --auto-tune every hour
5) Additional Steps for optional support:
   - Variety, Auto wallpaper changer, it will pull from any sites set and predefined sites for nasa images
