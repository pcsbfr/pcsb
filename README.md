
<p align="center">
  <img src="assets/logo.png" alt="PCSB Logo" width="320">
</p>

[!WARNING] ### Read this before starting PCSB USB Creator formats
USB drives, and the PCSB Mini OS can erase an internal disk.

Back up anything important first. Only use PCSB on computers and
storage devices that you own or are explicitly authorized to modify.

📋 What you need

   Requirement

🖥️   Windows 10 or Windows 11 PC
🔐   Authorized administrator access
💾   2 USB drives
🛠️   PCSB USB Creator
1️⃣   PCSB-WIPE-FINAL.iso
2️⃣   PCSB-FINAL-TEST.iso

The two USB drives

Drive                   Image                   Role

USB 1 --- Mini OS   PCSB-WIPE-FINAL.iso   Boot PCSB Mini OS and
prepare the target PC

🔐 1. Administrator access

PCSB USB Creator needs administrator privileges because it accesses and
reformats physical USB drives.

Normal method

Right-click PCSB USB Creator → Run as administrator, then
approve the Windows UAC prompt.

[!TIP] If Windows asks for administrator credentials, use an account
that is authorized to administer the computer.

Optional dedicated PCSB account

If you are already inside an authorized elevated Command Prompt, you
can create a dedicated local account:

net user PCSBAdmin * /add
net localgroup Administrators PCSBAdmin /add

On some French Windows installations:

net localgroup Administrateurs PCSBAdmin /add

[!IMPORTANT] These commands require an already-authorized
administrator session. They are not a method for bypassing an
administrator password, parental/organization restrictions, or another
computer's security.

💾 2. Create USB 1 --- PCSB Mini OS

Connect your first USB drive and open PCSB USB Creator.

Find PCSB Mini OS USB.

Select the correct USB drive.

Check the disk number, model and capacity.

Click Flash USB.

Confirm the erase warning.

Wait until the operation finishes.

[!CAUTION] ## ⚠️ USB 1 WILL BE ERASED Everything currently stored
on the selected USB drive will be permanently deleted.

Check the drive model and capacity before confirming.

When finished:

USB 1
└── PCSB Mini OS
    └── Source: PCSB-WIPE-FINAL.iso

💿 3. Create USB 2 --- PCSB Installer

Connect your second USB drive.

Find PCSB Installation USB.

Select the second USB drive.

Verify its model and capacity.

Click Flash USB.

Confirm the warning.

Wait for completion.

[!NOTE] If install.wim is too large for FAT32, PCSB USB Creator
automatically splits it into .swm files. This is normal and Windows
Setup supports this installation format.

When finished:

USB 2
└── PCSB Installation
    └── Source: PCSB-FINAL-TEST.iso

🚀 4. Boot PCSB from USB

Connect USB 1 --- PCSB Mini OS to the target computer.

Shut down the PC, turn it back on, and immediately open the
manufacturer's one-time boot menu.

Manufacturer   Common boot key

HP             Esc → F9
Dell           F12
Lenovo         F12
ASUS           Esc
Acer           F12
MSI            F11

Then select something similar to:

UEFI: <your USB drive>

[!TIP] Prefer the one-time boot menu instead of permanently
changing the boot order.

🛠️ 5. USB does not appear?

If Windows still starts normally, enter the firmware through Windows
Advanced Startup.

Windows 11

Go to:

Settings
   ↓
System
   ↓
Recovery
   ↓
Advanced startup
   ↓
Restart now

After the computer restarts:

Troubleshoot
   ↓
Advanced options
   ↓
UEFI Firmware Settings
   ↓
Restart

Your computer should enter its BIOS/UEFI settings.

⚙️ 6. Check the BIOS / UEFI

Look for sections named something similar to:

Boot

Boot Options

Boot Order

Startup

UEFI Boot

Check that USB boot is available.

Save your changes, restart the computer, open the one-time boot menu
again, and select the PCSB USB.

[!NOTE] Firmware menus differ between manufacturers and models, so
the exact names may be different.

🔄 7. Restore BIOS / UEFI defaults

If boot settings were changed previously, use the firmware's built-in
reset option.

Look for:

Load Setup Defaults
Restore Defaults
Load Optimized Defaults
Factory Defaults

Confirm it, then select Save & Exit.

[!WARNING] ### Do not use hardware password-bypass tricks Removing
a CMOS/RTC battery is not a universal BIOS-password reset method
on modern PCs.

This guide does not cover shorting motherboard pins, master-password
generators, or defeating firmware security.

If your own computer has a firmware password you cannot recover, use
the manufacturer's official recovery procedure.

🧹 8. Start PCSB Mini OS

Boot from USB 1.

PCSB Mini OS is the preparation environment used before installing the
full system.

Before erasing anything, verify:

Disk model

Disk capacity

Serial number

Bus type

[!CAUTION] # ⚠️ DISK ERASURE Preparing the target disk can
permanently remove the existing operating system, partitions and
personal files.

Never assume that Disk 0 is automatically the correct disk.

🪟 9. Install PCSB

After the target disk has been prepared:

Use USB 2 --- PCSB Installation.

Start PCSB Setup.

Select the intended empty target disk.

Continue through Windows Setup.

Wait for installation and the first PCSB boot.

🗺️ Complete PCSB workflow

┌──────────────────────────┐
│   PCSB USB Creator       │
└────────────┬─────────────┘
             │
      ┌──────┴──────┐
      ▼             ▼
┌───────────┐  ┌──────────────┐
│   USB 1   │  │    USB 2     │
│ Mini OS   │  │ Installation │
└─────┬─────┘  └──────┬───────┘
      │               │
      ▼               │
 Boot target PC       │
      │               │
      ▼               │
 PCSB Mini OS         │
      │               │
      ▼               │
 Verify target disk   │
      │               │
      ▼               │
 Prepare target disk  │
      │               │
      └───────┬───────┘
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

PCSB must be able to locate:

PCSB-WIPE-FINAL.iso
PCSB-FINAL-TEST.iso

Verify that both installation images are present in the PCSB data
directory.

❌ No USB drive detected

Disconnect and reconnect the USB drive.

Wait a few seconds.

Click Refresh.

Check that Windows detects the USB drive.

Try another USB port.

❌ USB created successfully but it does not boot

Try, in order:

The manufacturer's one-time boot menu.

The explicit UEFI entry for the USB.

Another USB port.

Advanced startup → UEFI Firmware Settings.

The firmware's built-in Restore Defaults option.

🔐 Administrator access unavailable

Use an authorized administrator account or ask the computer's
owner/administrator to approve the UAC request.

[!IMPORTANT] ## Final safety check Before every destructive
operation, check what physical disk PCSB selected.

A wrong disk selection can permanently destroy data.
