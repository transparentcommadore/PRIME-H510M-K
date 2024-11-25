[GUIDE] Installing macOS Monterey (12.x) / Ventura (13.x) / Sonoma (14.x) / Sequoia (15.x) on Asus Prime H510M-K

OpenCore 0.9.9 - 1.0.2

OPENCORE bootloader for installation on 10-gn processors (Intel Comet Lake-S) EFI for Asus Prime H510M-K DDR4 motherboard.

Add extra kexts:
IntelMausi for Intel Ethernet
AppleALC for universial patch audio
WhateverGreen for enable GPU AMD
Lilu for patches
AllUSBInject for init and mapping USB 2.0/3.0
VirtualSMC
Intel Airportitlwm, IntelBluetoothFirmware for AX210

Custom ACPI (optional)

SSDT-AWAC-DISABLE.aml;
SSDT-EC-USBX.aml;
SSDT-PLUG-ALT.aml;

Disabled:
Fast Boot;
VT-d (enable if DisableMapper Quirks set True);
CFG Lock;
Secure Boot;
Parallel Port;
Serial Port;
Resizable BAR Support;

Enabled:
VT-x
UEFI startup mode
Above 4G decoding
Hyper-Threading
Execute Disable Bit
EHCI/XHCI Hand-off
OS type: Windows 10 UEFI Mode
PCI-e x16 switched to Gen3.0 (If Videocard connect to PCI-e x16 Riser)
OC - boot-args:

keepsyms=1 debug=0x100 agdpmod=pikera -wegnoigpu alcid=66 -v
