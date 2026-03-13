# Dell Latitude E7470 - OpenCore + macOS Ventura

> OpenCore-based Hackintosh for the Dell Latitude E7470 with Intel Core i7-6600U and **BCM94360NG** (native Broadcom) Wi-Fi/Bluetooth.  
> This configuration prioritizes a stable, snappy experience as close as possible to a real MacBook, with native Bluetooth, AirDrop, Sidecar and iPhone Continuity features working out of the box, using the fewest kexts possible.

[![macOS](https://img.shields.io/badge/macOS-Ventura_13.x-informational?style=flat&logo=apple&logoColor=white&color=black)](https://www.apple.com/macos/ventura/)
[![OpenCore](https://img.shields.io/badge/OpenCore-1.0.6-informational?style=flat&color=0075FF)](https://github.com/acidanthera/OpenCorePkg)
[![Hardware](https://img.shields.io/badge/Hardware-Dell_Latitude_E7470-informational?style=flat&color=007DB8)](https://www.dell.com)
[![Status](https://img.shields.io/badge/Status-Stable-success?style=flat)](https://github.com/vibecoderbr)

---

## 🖥️ My Hardware

| Component | Specification |
|---|---|
| Model | Dell Latitude E7470 |
| Processor | Intel Core i7-6600U @ 2.80GHz · 3MB L3 cache |
| Processor Family | Skylake · 6th generation · 14nm · Q3'15 |
| Graphics | Integrated Intel HD Graphics 520 |
| Memory | 16GB 2133MHz DDR4 SDRAM (Dual Channel) |
| Display | 14" QHD (2560×1440) · Touch LCD |
| Storage | 256GB M.2 SATA SSD |
| Audio | RealTek ALC3235 · 24-bit · layout-id `11` |
| WLAN + Bluetooth | Fenvi BCM94360NG · IEEE 802.11 ac/a/b/g/n · BT 4.0 |
| LAN | Ethernet 10/100/1000 Mb/s (RJ-45) |
| Camera | 1920×1080 FHD Webcam |
| Fingerprint Reader | Yes |
| USB 3.0 | 2× USB 3.0 + 1× PowerShare (right side) |
| SD Card | SD 4.0 |
| Smart Card | Yes |
| Keyboard | ABNT2 Backlit Keyboard |
| Trackpad | ALPS Touchpad |
| SMBIOS | `MacBookPro14,1` |

---

## ✅ What's Working

| Functionality | Status | Dependencies |
|---|---|---|
| Intel HD 520 Graphics *(including graphics acceleration)* | ✅ Working | [WhateverGreen](https://github.com/acidanthera/WhateverGreen) |
| All USB ports | ✅ Working | [USBPorts.kext](EFI/OC/Kexts/USBPorts.kext) (custom mapping) |
| Internal camera | ✅ Working | Native |
| WiFi | ✅ Working | Native · BCM94360NG |
| Bluetooth | ✅ Working | [BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM) |
| Shutdown / Reboot / Sleep / Wake | ✅ Working | SSDT-E7470 · GPRW patch |
| Speakers and headphone jack | ✅ Working | [AppleALC](https://github.com/acidanthera/AppleALC) · layout-id `11` · [VerbStub](https://github.com/hackintosh-stuff/ComboJack) |
| Intel Gigabit Ethernet | ✅ Working | [IntelMausi](https://github.com/acidanthera/IntelMausi) |
| iCloud Services | ✅ Working | Requires unique SMBIOS |
| Continuity<br>&nbsp;• *Handoff*<br>&nbsp;• *Universal Clipboard*<br>&nbsp;• *Sidecar*<br>&nbsp;• *Universal Control*<br>&nbsp;• *Continuity Camera*<br>&nbsp;• *Instant Hotspot*<br>&nbsp;• *iPhone Cellular Calls / SMS* | ✅ Working | Native · BCM94360NG |
| AirDrop | ✅ Working | Native · BCM94360NG |
| AirPlay | ✅ Working | Native · BCM94360NG |
| miniDP and HDMI with digital audio passthrough | ✅ Working | [WhateverGreen](https://github.com/acidanthera/WhateverGreen) |
| Keyboard + backlight | ✅ Working | [VoodooPS2](https://github.com/SkyrilHD/VoodooPS2) · [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys) |
| Trackpad with multitouch gestures | ✅ Working | [VoodooPS2](https://github.com/SkyrilHD/VoodooPS2) |
| SD Card Reader | ✅ Working | [RealtekCardReader](https://github.com/0xFireWolf/RealtekCardReader) · [RealtekCardReaderFriend](https://github.com/0xFireWolf/RealtekCardReaderFriend) |
| Battery status | ✅ Working | [SMCBatteryManager](https://github.com/acidanthera/VirtualSMC) |
| CPU / thermal sensors | ✅ Working | [SMCProcessor](https://github.com/acidanthera/VirtualSMC) · [SMCDellSensors](https://github.com/acidanthera/VirtualSMC) |
| Touchscreen | ⚠️ Not tested / ❌ Not supported | — |
| Fingerprint Reader | ⚠️ Not tested / ❌ Not supported | — |
| Smart Card | ⚠️ Not tested / ❌ Not supported | — |

---

## 🛠️ Recommended Tools

| Tool | Purpose |
|---|---|
| [OC Auxiliary Tools](https://github.com/ic005k/OCAuxiliaryTools) | Visual config.plist editor with built-in kext updater and OC validation |
| [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) | Generate unique SMBIOS |
| [ProperTree](https://github.com/corpnewt/ProperTree) | Edit config.plist |
| [MountEFI](https://github.com/corpnewt/MountEFI) | Mount EFI partition |
| [USBToolBox](https://github.com/USBToolBox/tool) | USB port mapping (Windows) |
| [Hackintool](https://github.com/benbaker76/Hackintool) | USB port visualization and diagnostics |
| [BetterDisplay](https://github.com/waydabber/BetterDisplay) | HiDPI scaling for internal display |

---

## 🧩 Kexts

| Kext | Version | Purpose |
|---|---|---|
| [Lilu](https://github.com/acidanthera/Lilu) | 1.7.2 | Kernel patching base |
| [VirtualSMC](https://github.com/acidanthera/VirtualSMC) | 1.3.8 | Apple SMC emulation |
| [SMCProcessor](https://github.com/acidanthera/VirtualSMC) | 1.3.8 | CPU sensors |
| [SMCDellSensors](https://github.com/acidanthera/VirtualSMC) | 1.3.8 | Dell thermal sensors |
| [SMCBatteryManager](https://github.com/acidanthera/VirtualSMC) | 1.3.8 | Battery status |
| [WhateverGreen](https://github.com/acidanthera/WhateverGreen) | 1.7.1 | Intel graphics patches |
| [AppleALC](https://github.com/acidanthera/AppleALC) | 1.9.7 | Native audio · layout-id `11` |
| [IntelMausi](https://github.com/acidanthera/IntelMausi) | 1.0.9 | Intel I219-LM Ethernet |
| [NVMeFix](https://github.com/acidanthera/NVMeFix) | 1.1.4 | NVMe compatibility |
| [BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM) | 2.7.2 | Bluetooth fix for native BCM |
| [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys) | 1.0.4 | Brightness hotkeys |
| [VoodooPS2Controller](https://github.com/SkyrilHD/VoodooPS2) | 1.0.7 | ALPS keyboard and trackpad |
| [RealtekCardReader](https://github.com/0xFireWolf/RealtekCardReader) | 0.9.7 | SD card reader |
| [RealtekCardReaderFriend](https://github.com/0xFireWolf/RealtekCardReaderFriend) | 1.0.4 | SD card reader compatibility |
| [USBPorts](EFI/OC/Kexts/USBPorts.kext) | 1.0 | Custom USB port mapping |
| [VerbStub](https://github.com/hackintosh-stuff/ComboJack) | 1.0.4 | Audio jack detection |

> **Note:** `BrcmPatchRAM3` and `BrcmFirmwareData` are present in the EFI but **disabled**. For the BCM94360NG, these kexts are unnecessary and may cause instability.

---

## 📦 Installation Guide

> **Note:** If your hardware is exactly as listed in the [My Hardware](#️-my-hardware) section, everything should work out of the box. If any component differs, you may need to adjust or swap kexts accordingly.

### Step 1 — Download OpenCore

This EFI was built and tested with **OpenCore 1.0.6**. Using a different version may cause `config.plist` validation errors or boot failures due to changes in quirks and driver compatibility.

🔗 [acidanthera/OpenCorePkg — Releases](https://github.com/acidanthera/OpenCorePkg/releases)

Extract the package and keep it handy — you'll use the utilities inside it in the next step.

### Step 2 — Download the macOS Ventura Recovery Image

You don't need a working Mac to get the installer. Use the `macrecovery` script included with OpenCore:

```bash
# Navigate to the macrecovery folder inside the OpenCore utilities
cd Utilities/macrecovery

# Download the macOS Ventura recovery image
python3 macrecovery.py -b Mac-4B682C642B45593E -m 00000000000000000 download
```

This will download a `BaseSystem.dmg` and `BaseSystem.chunklist` to the current folder. Copy both files to your USB drive alongside the OpenCore EFI.

> **USB formatting:** Format your USB as **FAT32 / MBR** before copying the files.  
> Full instructions: [Dortania — Making the installer](https://dortania.github.io/OpenCore-Install-Guide/installer-guide/)

### Step 3 — Download and Copy the EFI

Download this repository and copy the `EFI` folder to the EFI partition of your USB drive.

Use **MountEFI** to mount the partition:

```
EFI/  ← copy this entire folder to the root of the EFI partition
├── BOOT/
└── OC/
```

### Step 4 — Generate Your SMBIOS

**Never use SMBIOS values from someone else's repository.** You must generate your own unique set.

Run **GenSMBIOS** and select option `3 — Generate SMBIOS`, using model `MacBookPro14,1`:

```
Type:         MacBookPro14,1
Serial:       [generated]
Board Serial: [generated]
SmUUID:       [generated]
```

> Verify your serial at [Apple's coverage check](https://checkcoverage.apple.com) — it should return **"Invalid Serial Number"**, confirming it doesn't belong to any real Mac.

### Step 5 — Configure the config.plist

Open `EFI/OC/config.plist` using **ProperTree** or **OC Auxiliary Tools** and fill in your SMBIOS values under `PlatformInfo > Generic`:

```xml
<key>SystemProductName</key>  →  MacBookPro14,1
<key>SystemSerialNumber</key> →  [your generated serial]
<key>MLB</key>                →  [your generated board serial]
<key>SystemUUID</key>         →  [your generated SmUUID]
```

If using ProperTree, run **Clean Snapshot** (`Cmd+Shift+R`) after saving to ensure all kexts and drivers are properly referenced.

### Step 6 — BIOS Settings

Enter the E7470 BIOS (`F2` at boot) and apply the following:

| Setting | Value |
|---|---|
| Secure Boot | **Disabled** |
| SATA Operation | **AHCI** |
| Boot Mode | **UEFI** |
| Fast Boot | **Disabled** |
| VT-d | **Disabled** |

### Step 7 — Install macOS

1. Boot from the USB (`F12` at startup to select boot device)
2. In the OpenCore picker, select **"Install macOS Ventura"**
3. Open **Disk Utility** and format the target drive as **APFS / GUID Partition Map**
4. Proceed with the installation — the system will reboot several times. Always select the USB in the OpenCore picker until the installation is complete
5. Once in macOS, use **MountEFI** to mount the internal drive's EFI partition and copy the `EFI` folder from the USB to it

---

## 📋 Kext Load Order

OpenCore loads kexts in the exact sequence defined in `config.plist`. Order matters — a kext that depends on another will fail silently if loaded first. The table below mirrors the order in this EFI and explains the reasoning behind each position.

| # | Kext | Purpose | Why this position |
|---|---|---|---|
| 0 | [Lilu](https://github.com/acidanthera/Lilu) | Kernel patching engine | **Must be first.** Every other kext in this list depends on Lilu as a base. Loading it after any plugin causes a boot failure. |
| 1 | [VirtualSMC](https://github.com/acidanthera/VirtualSMC) | Apple SMC emulation | Requires Lilu. Must come before its own plugins (SMCProcessor, SMCDellSensors, SMCBatteryManager), which will not load without it. |
| 2 | [SMCProcessor](https://github.com/acidanthera/VirtualSMC) | CPU temperature sensors | VirtualSMC plugin — must follow VirtualSMC. |
| 3 | [SMCDellSensors](https://github.com/acidanthera/VirtualSMC) | Dell fan and thermal sensors | VirtualSMC plugin — must follow VirtualSMC. Dell-specific; provides more accurate readings than SMCProcessor alone on this hardware. |
| 4 | [SMCBatteryManager](https://github.com/acidanthera/VirtualSMC) | Battery status and percentage | VirtualSMC plugin — must follow VirtualSMC. |
| 5 | [WhateverGreen](https://github.com/acidanthera/WhateverGreen) | Intel HD 520 graphics patches | Requires Lilu. Loaded early because GPU initialization happens at boot — delays can cause a black screen. |
| 6 | [AppleALC](https://github.com/acidanthera/AppleALC) | Native audio · layout-id `11` | Requires Lilu. Placed after WhateverGreen since both patch device properties; loading order prevents conflicts on the same PCI bus. |
| 7 | [NVMeFix](https://github.com/acidanthera/NVMeFix) | NVMe power management fix | Requires Lilu. No strict dependency on position, placed here as a standalone hardware fix before input drivers. |
| 8 | [IntelMausi](https://github.com/acidanthera/IntelMausi) | Intel I219-LM Ethernet | Standalone driver, no Lilu dependency. Loaded before input kexts by convention. |
| 9 | [VoodooPS2Controller](https://github.com/SkyrilHD/VoodooPS2) | ALPS keyboard and trackpad controller | Parent kext — must be loaded before its own plugins (VoodooInput, VoodooPS2Keyboard, VoodooPS2Trackpad). |
| 10 | [VoodooInput](https://github.com/SkyrilHD/VoodooPS2) | Multitouch gesture engine | VoodooPS2 plugin — must follow the parent controller. |
| 11 | [VoodooPS2Keyboard](https://github.com/SkyrilHD/VoodooPS2) | Keyboard HID mapping | VoodooPS2 plugin — depends on VoodooInput being already initialized. |
| 12 | [VoodooPS2Trackpad](https://github.com/SkyrilHD/VoodooPS2) | ALPS trackpad with gestures | VoodooPS2 plugin — depends on both VoodooInput and VoodooPS2Keyboard. |
| 13 | [BrightnessKeys](https://github.com/acidanthera/BrightnessKeys) | Brightness hotkeys (Fn+F6/F7) | Requires Lilu and benefits from VoodooPS2Keyboard being loaded first to correctly intercept key events. |
| 14 | ~~[BrcmPatchRAM3](https://github.com/acidanthera/BrcmPatchRAM)~~ | ~~Intel Bluetooth firmware uploader~~ | ⚠️ **Disabled.** Not needed for BCM94360NG. Kept in the EFI for reference only — enabling it will cause Bluetooth instability. |
| 15 | ~~[BrcmFirmwareData](https://github.com/acidanthera/BrcmPatchRAM)~~ | ~~Intel Bluetooth firmware data~~ | ⚠️ **Disabled.** Same reason as above — BCM94360NG is natively supported and does not require firmware injection. |
| 16 | [BlueToolFixup](https://github.com/acidanthera/BrcmPatchRAM) | Bluetooth stack fix for macOS 12+ | Requires Lilu. Must load after the disabled Brcm kexts to avoid initialization conflicts in the Bluetooth stack. |
| 17 | [RealtekCardReader](https://github.com/0xFireWolf/RealtekCardReader) | Realtek SD card reader driver | Standalone driver. No strict ordering requirement; placed late as a peripheral device. |
| 18 | [RealtekCardReaderFriend](https://github.com/0xFireWolf/RealtekCardReaderFriend) | Card reader macOS compatibility shim | Must follow RealtekCardReader — it patches the parent kext's behavior for macOS compatibility. |
| 19 | [USBPorts](EFI/OC/Kexts/USBPorts.kext) | Custom USB port map for E7470 | Standalone injector kext. Loaded late to override any previously assigned port personalities. |
| 20 | [VerbStub](https://github.com/hackintosh-stuff/ComboJack) | Audio jack plug/unplug detection | Loaded last as it depends on AppleALC having already patched the audio device. |

---

## ⚙️ Post-installation

### SMBIOS and Apple ID

Sign in to your Apple ID **only after applying your unique SMBIOS**. If the system requests additional verification, approve it — this is expected on the first hardware association.

### Bluetooth (BCM94360NG)

The BCM94360NG is recognized natively by macOS — no firmware injection or additional kexts required. The EFI in this repository is already configured correctly for this chip.

### USB Mapping

Correct USB mapping is the foundation for everything to work properly on this build. The E7470 has internal USB ports used by both the Bluetooth module and the webcam — if any of them are mapped incorrectly, Bluetooth may appear as disconnected or the toggle may behave unexpectedly.

The `USBPorts.kext` included in this EFI already has the correct mapping for the E7470. If you ever need to inspect or rebuild it:

- Open **Hackintool** (USB tab) and identify each port by its `LocationID`
- The Bluetooth and webcam ports must both be set to `Internal` (type `255`)
- After any changes, run **Clean Snapshot** in ProperTree (`Cmd+Shift+R`) and reset NVRAM on next boot

### HiDPI Scaling

For the QHD 2560×1440 display, the recommended scale is **81%** (equivalent to a sharp 2064×1161). Configure this with **BetterDisplay** after installation.

---

## 📁 EFI Structure

```
EFI/                                # OpenCore 1.0.6
├── BOOT/
│   └── BOOTx64.efi
└── OC/
    ├── ACPI/
    │   └── SSDT-E7470.aml          # Custom SSDT (USB, audio, sleep)
    ├── Drivers/
    │   ├── OpenRuntime.efi
    │   ├── OpenCanopy.efi
    │   └── AudioDxe.efi
    ├── Kexts/
    │   ├── Lilu.kext
    │   ├── VirtualSMC.kext
    │   ├── WhateverGreen.kext
    │   ├── AppleALC.kext
    │   ├── IntelMausi.kext
    │   ├── BlueToolFixup.kext
    │   ├── VoodooPS2Controller-SkyrilHD.kext
    │   ├── BrightnessKeys.kext
    │   ├── RealtekCardReader.kext
    │   ├── RealtekCardReaderFriend.kext
    │   ├── USBPorts.kext
    │   └── VerbStub.kext
    ├── Resources/                   # OpenCanopy themes
    ├── Tools/
    └── config.plist
```

---

## 🙏 Credits

- [Acidanthera](https://github.com/acidanthera) — OpenCore, Lilu, VirtualSMC, WhateverGreen, AppleALC and all related kexts
- [Dortania](https://dortania.github.io/OpenCore-Install-Guide/) — Reference documentation
- [0xFireWolf](https://github.com/0xFireWolf) — RealtekCardReader
- [SkyrilHD](https://github.com/SkyrilHD) — VoodooPS2 for ALPS
- [ic005k](https://github.com/ic005k/OCAuxiliaryTools) — OC Auxiliary Tools
- [r/hackintosh](https://reddit.com/r/hackintosh) community
- [vpcano](https://github.com/vpcano/Hackintosh_OC_Ventura_LatitudeE7470) — Base EFI used for this project
- [jessylou](https://github.com/jessylou/Dell-Latitude-E7470-OpenCore-Ventura) — EFI didn't boot on this hardware, but provided key insights during troubleshooting

---

<div align="center">

Made with ☕ by [vibecoderbr](https://github.com/vibecoderbr) · March 2026

</div>
