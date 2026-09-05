
<p align="center">
  <img src="assets/logo.png" alt="PCSB Logo" width="320">
</p>

<div align="center">

💻 PCSB

Clean. Simple. Yours.

Complete installation guide

</div>

[!WARNING]

Read this before starting

PCSB USB Creator formats USB drives, and PCSB Mini OS can erase an internal disk.

Back up all important files first. Only use PCSB on computers and storage devices that you own or are explicitly authorized to modify.

📋 What you need

Requirement

Description

🖥️ Computer

Windows 10 or Windows 11

🔐 Permissions

Authorized administrator access

💾 USB drives

Two USB drives

🛠️ Software

PCSB USB Creator

1️⃣ Mini OS

PCSB-WIPE-FINAL.iso

2️⃣ Installer

PCSB-FINAL-TEST.iso

[!NOTE]
USB 1 contains the PCSB Mini OS. USB 2 contains the full PCSB installer.

🔐 1. Administrator access

Right-click PCSB USB Creator → Run as administrator, then approve the UAC prompt.

[!TIP]
If Windows requests administrator credentials, use an account authorized to administer the computer.

If you are already in an authorized elevated Command Prompt, you can optionally create a dedicated PCSB account:

net user PCSBAdmin * /add
net localgroup Administrators PCSBAdmin /add

On some French Windows installations:

net localgroup Administrateurs PCSBAdmin /add

[!IMPORTANT]
These commands require an already-authorized administrator session. They are not a method for bypassing an administrator password or other security restrictions.

💾 2. Create USB 1 — PCSB Mini OS

Connect the first USB drive.

Open PCSB USB Creator as administrator.

Find PCSB Mini OS USB.

Select the correct USB.

Verify the disk number, model and capacity.

Click Flash USB.

Confirm and wait for completion.

[!CAUTION]

⚠️ USB 1 WILL BE ERASED

Everything on the selected USB drive will be permanently deleted.

Check the drive model and capacity before confirming.

USB 1
└── PCSB Mini OS
    └── PCSB-WIPE-FINAL.iso

💿 3. Create USB 2 — PCSB Installer

Connect the second USB drive.

Find PCSB Installation USB.

Select the second USB.

Verify its disk number, model and capacity.

Click Flash USB.

Confirm and wait for completion.

[!CAUTION]

⚠️ USB 2 WILL BE ERASED

Everything on the selected second USB drive will be permanently deleted.

[!NOTE]
If install.wim is too large for FAT32, PCSB USB Creator automatically splits it into .swm files. This is expected.

USB 2
└── PCSB Installation
    └── PCSB-FINAL-TEST.iso

🚀 4. Boot from USB

Connect USB 1 — PCSB Mini OS, shut down the computer, turn it on, and immediately open the manufacturer's one-time boot menu.

Manufacturer

Common key

HP

Esc → F9

Dell

F12

Lenovo

F12

ASUS

Esc

Acer

F12

MSI

F11

Select:

UEFI: <your USB drive>

[!TIP]
Prefer the one-time boot menu instead of permanently changing the boot order.

🛠️ 5. USB does not appear?

If Windows still starts normally:

Settings → System → Recovery → Advanced startup → Restart now

Then select:

Troubleshoot
    ↓
Advanced options
    ↓
UEFI Firmware Settings
    ↓
Restart

[!NOTE]
Menu names can vary slightly depending on Windows and the computer manufacturer.

⚙️ 6. BIOS / UEFI settings

Look for sections such as:

Boot

Boot Options

Boot Order

Startup

UEFI Boot

Check that USB boot is available, save any changes, restart, and select the PCSB USB from the one-time boot menu.

🔄 7. Restore BIOS / UEFI defaults

If firmware settings were changed previously, look for:

Load Setup Defaults
Restore Defaults
Load Optimized Defaults
Factory Defaults

Confirm, then choose Save & Exit.

[!WARNING]

BIOS / UEFI security

Removing the CMOS/RTC battery is not a universal BIOS-password reset method on modern PCs.

If your own computer has a firmware password you cannot recover, use the manufacturer's official recovery procedure.

🧹 8. Start PCSB Mini OS

Boot from USB 1.

Before erasing anything, verify:

Disk model

Capacity

Serial number

Bus type

[!CAUTION]

⚠️ INTERNAL DISK ERASURE

Preparing the target disk can permanently remove the operating system, partitions and personal files.

Never assume Disk 0 is automatically the correct disk.

🪟 9. Install PCSB

After preparing the intended target disk:

Use USB 2 — PCSB Installation.

Start PCSB Setup.

Select the intended empty target disk.

Continue through Windows Setup.

Complete the first PCSB boot.

🗺️ Complete workflow

PCSB USB Creator
       │
       ├──────────────┐
       ▼              ▼
 USB 1 Mini OS    USB 2 Installer
       │              │
       ▼              │
 Boot USB 1           │
       │              │
       ▼              │
 PCSB Mini OS         │
       │              │
       ▼              │
 Verify target disk   │
       │              │
       ▼              │
 Prepare disk         │
       └──────┬───────┘
              ▼
         PCSB Setup
              │
              ▼
         Install PCSB
              │
              ▼
        ✅ PCSB Ready

🔧 Troubleshooting

❌ PCSB USB Creator shows MISSING

Verify that PCSB can access:

PCSB-WIPE-FINAL.iso
PCSB-FINAL-TEST.iso

❌ No USB drive detected

Disconnect and reconnect it.

Wait a few seconds.

Click Refresh.

Check that Windows detects it.

Try another USB port.

❌ USB created but does not boot

Try the one-time UEFI boot menu.

Select the explicit UEFI USB entry.

Try another USB port.

Use Advanced startup → UEFI Firmware Settings.

Check USB boot settings.

Restore firmware defaults if appropriate.

🔐 Administrator access unavailable

Use an authorized administrator account or ask the owner/administrator to approve the UAC request.

[!IMPORTANT]

Final safety check

Before every destructive operation, verify the physical disk model, capacity and identity.

Selecting the wrong disk can permanently destroy data.

[!CAUTION]
Test disk-erasure features on a disposable test disk or virtual machine whenever possible.

<div align="center">

💻 PCSB

Clean. Simple. Yours.

For systems and storage devices you own or are explicitly authorized to modify.

</div>
