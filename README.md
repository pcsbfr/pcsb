# pcsb
<p align="center">
  <img src="assets/logo.png" alt="PCSB Logo" width="320">
</p>

<h1 align="center">PCSB</h1>

<p align="center">
  A lightweight, customized Windows experience built for clean and simple installations.
</p>

<p align="center">
  <strong>Simple. Clean. Ready to use.</strong>
</p>

---

## About PCSB

PCSB is a customized Windows installation designed to provide a lightweight, clean and straightforward experience.

It includes a customized installation environment, PCSB branding and a simple installation process.

> [!IMPORTANT]
> PCSB is intended for computers that you own or are authorized to erase and reinstall.
> Always back up your important files before starting.

## Download

Download the latest PCSB release from the **Releases** section of this repository.

You will need:

- A PCSB ISO
- A USB drive
- PCSB Flasher
- A compatible Windows PC

## Installation

### 1. Create your PCSB USB

1. Download the latest PCSB ISO.
2. Connect your USB drive.
3. Run `PCSB-Flasher.cmd` as Administrator.
4. Select your USB drive.
5. Confirm the operation.
6. Wait for the flashing process to finish.

> [!WARNING]
> All data stored on the selected USB drive will be erased.

### 2. Prepare for a clean installation

Back up everything you want to keep.

Run the PCSB clean-install preparation tool as Administrator and carefully verify the selected system disk before confirming the operation.

> [!CAUTION]
> This operation permanently erases the selected system disk, including Windows, applications and personal files.

### 3. Verify the clean state

After the disk has been erased:

1. Keep the PCSB USB disconnected.
2. Start the computer once.
3. Verify that the previous operating system no longer boots.
4. Turn the computer off.

A `No bootable device`, `No operating system` or firmware screen may appear.

### 4. Install PCSB

1. Connect the PCSB USB drive.
2. Turn on the computer.
3. Start from the PCSB USB drive.
4. Wait for PCSB Setup to appear.
5. Select the unallocated space on the empty internal drive.
6. Continue the installation.

PCSB Setup will create the required partitions automatically.

### 5. Finish setup

Complete the initial setup until you reach the PCSB desktop.

Then run:

```text
Finish PCSB.cmd
```

Follow the on-screen instructions and restart the computer when requested.

## Requirements

- 64-bit compatible PC
- UEFI firmware
- USB drive
- Enough storage for Windows
- Administrator access when creating the installation media

## Disclaimer

PCSB is an independent project and is not affiliated with or endorsed by Microsoft.

Windows is a trademark of Microsoft Corporation.

PCSB must only be used on computers you own or have permission to reinstall.

---

<p align="center">
  <strong>PCSB</strong><br>
  Clean Windows. Simple installation.
</p>
