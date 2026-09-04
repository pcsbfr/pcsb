
<p align="center">
  <img src="assets/logo.png" alt="PCSB Logo" width="320">
</p>

<h1 align="center"></h1>

<p align="center">
  A lightweight, customized Windows experience built for clean and simple installations.
</p>

<p align="center">
  <strong>Simple. Clean. Ready to use.</strong>
</p>

---

PCSB --- Complete Installation Guide

PCSB is a customized Windows installation designed around a simple
two-USB workflow.

[!WARNING] PCSB can erase entire disks and USB drives. Back up
important data before continuing. Only use PCSB on computers and
storage devices that you own or are explicitly authorized to modify.

1. What You Need

A Windows 10 or Windows 11 PC

Administrator authorization

Two USB drives

PCSB USB Creator

PCSB-WIPE-FINAL.iso

PCSB-FINAL-TEST.iso

USB     Image                   Purpose

USB 1   PCSB-WIPE-FINAL.iso   PCSB Mini OS / disk preparation
USB 2   PCSB-FINAL-TEST.iso   Full PCSB installation

2. Administrator Access

PCSB USB Creator requires administrator privileges to access,
repartition and format physical USB drives.

Normally, right-click PCSB USB Creator → Run as administrator, then
approve the Windows UAC prompt.

If you already have an authorized administrator session, you can
optionally create a dedicated local PCSB account from an elevated
Command Prompt:

net user PCSBAdmin * /add
net localgroup Administrators PCSBAdmin /add

On a French Windows installation, the localized group name may be:

net localgroup Administrateurs PCSBAdmin /add

[!IMPORTANT] These commands must be run from an already-authorized
elevated administrator session. They are not a method for bypassing an
administrator password or organizational restrictions.

3. Create USB 1 --- PCSB Mini OS

Connect the first USB drive.

Open PCSB USB Creator as administrator.

Under PCSB Mini OS USB, select the correct USB.

Verify its model and capacity.

Select Flash USB.

Confirm the erase operation.

Wait for completion.

[!CAUTION] Everything on the selected USB drive will be erased.

4. Create USB 2 --- PCSB Installation

Connect the second USB drive.

Under PCSB Installation USB, select it.

Verify its model and capacity.

Select Flash USB.

Confirm the erase operation.

Wait for completion.

PCSB USB Creator automatically handles the FAT32 file-size limitation by
splitting a large install.wim when necessary.

5. Boot from USB

Try the manufacturer's normal one-time boot menu first. Common keys
include F9, F10, F11, F12, Esc, or Del, depending on the computer.

Shut down the computer.

Connect USB 1 --- PCSB Mini OS.

Turn it on.

Immediately press the manufacturer's boot-menu key.

Select the UEFI entry for the PCSB USB drive.

Common examples:

Manufacturer   Common boot-menu key

HP             Esc / F9
Dell           F12
Lenovo         F12
ASUS           Esc
Acer           F12
MSI            F11

6. If USB Boot Is Unavailable --- Advanced Startup

If Windows still starts normally:

Settings → System → Recovery → Advanced startup → Restart now

Then:

Troubleshoot → Advanced options → UEFI Firmware Settings → Restart

In the firmware interface:

Check that USB boot is enabled or available.

Check the boot menu or boot order.

To undo previous firmware changes, use Load Setup Defaults,
Restore Defaults, or Optimized Defaults.

Save and restart.

Open the one-time boot menu and select the PCSB USB.

Exact names vary by manufacturer.

7. Resetting BIOS/UEFI Safely

Prefer the firmware's built-in Restore Defaults option or the
manufacturer's documented recovery procedure.

Removing the CMOS/RTC battery is not a universal password-reset method
on modern computers. This guide does not provide instructions for
removing the battery, shorting motherboard pins, using master passwords,
or otherwise defeating firmware passwords or security controls.

If firmware is password-locked and you are the legitimate owner, use the
manufacturer's official recovery/support process.

8. Start PCSB Mini OS

Boot from USB 1 --- PCSB Mini OS.

Before erasing anything, verify the target disk carefully:

Model

Capacity

Serial number

Bus type

[!CAUTION] Never assume that Disk 0 is automatically the correct
Windows disk.

9. Install PCSB

After preparing the target disk, use USB 2 --- PCSB Installation.

Start the PCSB installer, select the intended empty target disk, and
continue through Windows Setup.

10. Complete Workflow

Install PCSB USB Creator
          ↓
Create USB 1 — PCSB Mini OS
          ↓
Create USB 2 — PCSB Installation
          ↓
Restart target computer
          ↓
Open UEFI Boot Menu
          ↓
Boot USB 1
          ↓
Start PCSB Mini OS
          ↓
Verify and prepare target disk
          ↓
Use USB 2
          ↓
Install PCSB
          ↓
First PCSB boot

11. Troubleshooting

PCSB USB Creator says MISSING

Verify that PCSB has access to:

PCSB-WIPE-FINAL.iso
PCSB-FINAL-TEST.iso

No USB drive is detected

Reconnect the drive, select Refresh, and verify that Windows itself
detects the USB device.

USB was created but does not boot

Try the one-time UEFI boot menu first. If it is still absent, enter
UEFI Firmware Settings through Windows Advanced Startup and check
the manufacturer's USB-boot settings.

Administrator access is unavailable

Do not bypass the restriction. Sign in with an authorized administrator
account or ask the owner/administrator to approve the UAC request.

Safety

PCSB USB Creator formats physical storage devices, and PCSB Mini OS can
erase an internal target disk. Always verify disk model, capacity, and
identifying information before confirming an erase operation.

PCSB is intended only for computers and storage devices that you own or
have explicit authorization to modify.
