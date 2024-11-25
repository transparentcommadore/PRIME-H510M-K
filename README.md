[GUIDE] Installing macOS Monterey (14.x) / Ventura (15.x) on PRIME-H510M-K [OpenCore 0.9.9 - 1.0.2]

OPENCORE bootloader for installation on 10-gn processors (Intel Comet Lake-S)
EFI for PRIME-H510K motherboard.

Add extra kexts

    IntelMausi for Intel Ethernet
    AppleALC for universial patch audio
    WhateverGreen for enable GPU AMD
    Lilu for patches
    USBports for init and mapping USB 2.0/3.0
    VirtualSMC
    Airportitlwm, IntelBluetoothFirmware (IOSkywalkFamily.kext, IO80211FamilyLegacy.kext - https://github.com/OpenIntelWireless/itlwm/issues/1009#issuecomment-2370919270) for AX210

Custom ACPI (optional)

    SSDT-AWAC.aml
    SSDT-EC.aml
    SSDT-PLUG.aml
    SSDT-PNLF-CFL.aml
    SSDT-PNLF.aml
    SSDT-USB-Reset.aml
    SSDT-USBX.aml

Disabled:

    Fast Boot
    VT-d (enable if DisableMapper Quirks set True)
    CFG Lock
    Secure Boot
    Parallel Port
    Serial Port
    Resizable BAR Support

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

    -v keepsyms=1 -lilubetaall -igfxblr -cdfon revpatch=sbvmm -btlfxallowanyaddr
