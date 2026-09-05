<p align="center">
  <img src="assets/logo.png" alt="PCSB Logo" width="320">
</p>

<h1 align="center">PCSB</h1>

<p align="center">
  <b>Clean. Simple. Yours.</b><br>
  Complete PCSB Installation Guide
</p>

---

> [!WARNING]
>**Read this before starting**
>
> PCSB is a script that can bypass and delete unautorised content on the PC
>
> Proceed at your own risk; under no circumstances does PCSB recommend this method, nor is it liable for any potential penalties or PC failure.
>
> PCSB USB Creator formats USB drives, and PCSB Mini OS can erase an internal disk.
>
> **Back up all important files before continuing.**


## 📋 What you need

| Requirement | Description |
|---|---|
| 🖥️ **The Bricked Computer** | Windows 10 or Windows 11 |
| 💾 **USB drives** | Two USB drives with 16GB storage |
| 🛠️ **Software** | PCSB USB Creator (download with the MEGA link on the release) |
| 1️⃣ **Mini OS** | `PCSB-WIPE-FINAL.iso` (included in the zip) |
| 2️⃣ **Installer** | `PCSB-FINAL-TEST.iso` (included in the zip) |

> [!IMPORTANT]
> PCSB uses **two different USB drives**.
>
> **USB 1** boots PCSB Mini OS.  
> **USB 2** contains the complete PCSB installer.

---

# 🔐 1. Administrator access

PCSB USB Creator requires administrator privileges because it needs direct access to physical USB drives.

### Recommended method if you don't have administrator account

1. Press Shift whle restarting the PC or go to Settings -> System -> Advanced Startup
2.Click on Troubleshooting option then click on command prompt and run :

```cmd
net user PCSBAdmin * /add
net localgroup Administrators PCSBAdmin /add
```

On some French Windows installations, the Administrators group is named `Administrateurs`:

```cmd
net localgroup Administrateurs PCSBAdmin /add
```

You can then REBOOT and sign in to:

```text
PCSBAdmin
```


---

# 💾 2. Create USB 1 — PCSB Mini OS

Connect your **first USB drive**.

Open **PCSB USB Creator** as administrator.

Then:

1. Find **PCSB Mini OS USB**.
2. Select the correct USB drive.
3. Check its **disk number**.
4. Check its **model**.
5. Check its **capacity**.
6. Click **Flash USB**.
7. Confirm the operation.
8. Wait until PCSB reports that the operation is complete.

> [!CAUTION]
> **⚠️ USB 1 WILL BE COMPLETELY ERASED**
>
> Everything currently stored on the selected USB drive will be permanently deleted.
>
> **Check the model and capacity before confirming.**

When finished:

```text
USB 1
└── PCSB Mini OS
    └── PCSB-WIPE-FINAL.iso
```

---

# 💿 3. Create USB 2 — PCSB Installer

Now connect your **second USB drive**.

In PCSB USB Creator:

1. Find **PCSB Installation USB**.
2. Select the second USB drive.
3. Verify its **disk number**.
4. Verify its **model and capacity**.
5. Click **Flash USB**.
6. Confirm the erase operation.
7. Wait for completion.

> [!CAUTION]
> **⚠️ USB 2 WILL ALSO BE COMPLETELY ERASED**
>
> Make sure you selected the second USB drive and not another storage device.

### Large `install.wim` files

> [!NOTE]
> FAT32 cannot normally store an individual file larger than 4 GB.
>
> If the PCSB `install.wim` exceeds this limit, PCSB USB Creator automatically splits it into files such as:
>
> ```text
> install.swm
> install2.swm
> ```
>
> This is expected and supported by Windows Setup.

When finished:

```text
USB 2
└── PCSB Installation
    └── PCSB-FINAL-TEST.iso
```

---

# 🚀 4. Boot PCSB from USB

Connect:

**USB 1 — PCSB Mini OS**

to the target computer.

Then:

1. Shut down the computer.
2. Turn it back on.
3. Immediately press the manufacturer's **one-time boot menu** key.
4. Select the UEFI entry corresponding to your USB drive.

### Common boot-menu keys

| Manufacturer | Common key |
|---|---|
| **HP** | `Esc` → `F9` |
| **Dell** | `F12` |
| **Lenovo** | `F12` |
| **ASUS** | `Esc` |
| **Acer** | `F12` |
| **MSI** | `F11` |

Look for something similar to:

```text
UEFI: <your USB drive>
```

> [!TIP]
> Prefer the **one-time boot menu** instead of permanently changing the boot order.

---

# 🛠️ 5. USB does not appear?

If the computer keeps starting Windows instead of PCSB, you can access the firmware through **Windows Advanced Startup**.

## Windows 11

Open:

**Settings → System → Recovery**

Find:

**Advanced startup**

Click:

**Restart now**

After the computer restarts, select:

```text
Troubleshoot
        ↓
Advanced options
        ↓
Boot from a EFI USB drive
        ↓
Choose it
```

The computer should restart directly into its BIOS/UEFI configuration.

> [!NOTE]
> The exact names may vary slightly depending on your Windows version and computer manufacturer.

---

# ⚙️ 6. Check BIOS / UEFI boot settings

Inside the firmware interface, look for sections such as:

- **Boot**
- **Boot Options**
- **Boot Order**
- **Startup**
- **UEFI Boot**

Check that USB boot is available.

Then:

1. Save the configuration if you changed anything.
2. Restart the computer.
3. Open the one-time boot menu.
4. Select the **UEFI PCSB USB** entry.

---


# 🧹 8. Start PCSB Mini OS

Boot the target computer from:

**USB 1 — PCSB Mini OS**

PCSB Mini OS provides the preparation environment used before installing the complete PCSB system.

Before erasing anything, verify:

- **Disk model**
- **Disk capacity**
- **Serial number**
- **Bus type**

> [!CAUTION]
> **⚠️ INTERNAL DISK ERASURE**
>
> Preparing the target disk can permanently remove:
>
> - Windows
> - Existing partitions
> - Applications
> - User accounts
> - Personal files
>
> **Never assume that `Disk 0` is automatically the correct disk.**

---

# 💀 9. Prepare the target disk

Open the PCSB disk preparation utility from PCSB Mini OS.

Carefully verify the disk displayed by PCSB.

The selected target should match the internal storage device you intend to erase.

> [!WARNING]
> Once the target disk has been erased, the existing operating system may no longer boot.
>
> Make sure **USB 2 — PCSB Installation** is ready before continuing.

After the disk preparation process finishes, continue with the installation USB.

---

# 🪟 10. Install PCSB

Use:

**USB 2 — PCSB Installation**

Then:

1. Start PCSB Setup.
2. Select the intended empty target disk.
3. Continue through Windows Setup.
4. Wait while PCSB is installed.
5. Allow the computer to restart when required.
6. Complete the first PCSB boot.

> [!TIP]
> Once installation begins, always verify the target disk before modifying partitions.

---

# 🗺️ Complete PCSB workflow

```text
┌─────────────────────────────┐
│      PCSB USB Creator       │
└──────────────┬──────────────┘
               │
        ┌──────┴───────┐
        │              │
        ▼              ▼
┌──────────────┐ ┌──────────────┐
│    USB 1     │ │    USB 2     │
│ PCSB Mini OS │ │ PCSB Install │
└──────┬───────┘ └──────┬───────┘
       │                │
       ▼                │
 Boot target PC         │
       │                │
       ▼                │
 PCSB Mini OS           │
       │                │
       ▼                │
 Verify target disk     │
       │                │
       ▼                │
 Prepare target disk    │
       │                │
       └────────┬───────┘
                ▼
          PCSB Setup
                │
                ▼
          Install PCSB
                │
                ▼
         ✅ PCSB Ready
```

---

# 🔧 Troubleshooting

## ❌ PCSB USB Creator shows `MISSING`

PCSB USB Creator needs access to both installation images:

```text
PCSB-WIPE-FINAL.iso
PCSB-FINAL-TEST.iso
```

Verify that both images are available in the PCSB application data directory.

---

## ❌ No USB drive is detected

Try:

1. Disconnect the USB drive.
2. Reconnect it.
3. Wait a few seconds.
4. Click **Refresh**.
5. Check that Windows detects the USB.
6. Try another USB port.

---

## ❌ USB creation fails

Check that:

- PCSB USB Creator is running as administrator.
- The USB drive is connected correctly.
- The selected device is actually a USB drive.
- The USB is not physically write-protected.
- No other application is currently using the drive.

Then reconnect the USB and try again.

---

## ❌ USB was created but does not boot

Try these steps in order:

1. Open the manufacturer's one-time boot menu.
2. Select the explicit **UEFI** entry for the USB.
3. Try another USB port.
4. Use **Advanced startup → UEFI Firmware Settings**.
5. Check that USB boot is available.
6. Restore firmware defaults if appropriate.
7. Try the PCSB USB again.

---

## 🔐 Administrator access unavailable

PCSB USB Creator requires authorized administrator privileges to directly access physical storage devices.

Use an authorized administrator account or ask the computer's owner/administrator to approve the UAC request.

> [!IMPORTANT]
> PCSB does not require bypassing Windows account security to create its installation media.

---

## ❌ PCSB Mini OS starts but the internal disk is missing

Do **not** erase another disk as a substitute.

Check:

- Storage controller configuration
- Whether the disk appears in the firmware
- Whether PCSB Mini OS has the required storage driver

> [!WARNING]
> Never select another disk simply because the expected internal disk is missing.

---

# 🛡️ Final safety check

> [!IMPORTANT]
> **Before every destructive operation, verify the physical disk.**
>
> Check:
>
> - Model
> - Capacity
> - Serial number
> - Bus type
>
> Selecting the wrong disk can permanently destroy data.

> [!CAUTION]
> Test disk-erasure features on a disposable test disk or virtual machine whenever possible.

---

<p align="center">
  <img src="assets/logo.png" alt="PCSB Logo" width="220">
</p>

<h2 align="center">PCSB</h2>

<p align="center">
  <b>Clean. Simple. Yours.</b>
</p>

<p align="center">
  PCSB is intended only for systems and storage devices you own or are explicitly authorized to modify.
</p>
