# Appendix: Ubuntu 22.04 Installation Guide

Complete guide for installing Ubuntu 22.04 LTS for SimToFly tutorials.

**Choose your installation method:**

- [Virtual Machine (Recommended for Beginners)](#virtual-machine-installation)
- [Dual Boot (Better Performance)](#dual-boot-installation)
- [Native Installation (Best Performance)](#native-installation)

---

## Virtual Machine Installation

**Best for:** Beginners, trying before committing, keeping current OS

**Pros:**

- Safe - doesn't modify your current system
- Easy to snapshot and restore
- Can run alongside Windows/macOS
- Easy to delete if you change your mind

**Cons:**

- Slower performance (especially Gazebo)
- Requires powerful host computer
- Shared resources with host OS

---

### Step 1: Install VirtualBox

**Download VirtualBox:**

- Visit: https://www.virtualbox.org/wiki/Downloads
- Download for your OS (Windows, macOS, or Linux)
- Install VirtualBox

**Verify installation:**

- Open VirtualBox
- Should see main window with no VMs

---

### Step 2: Download Ubuntu 22.04 ISO

**Download:**

- Visit: https://ubuntu.com/download/desktop
- Click "Download Ubuntu 22.04.x LTS"
- Save ISO file (~4GB download)

**File name:** `ubuntu-22.04.x-desktop-amd64.iso`

---

### Step 3: Create Virtual Machine

**In VirtualBox, click "New":**

**Basic settings:**
```
Name: SimToFly-Ubuntu
Type: Linux
Version: Ubuntu (64-bit)
```

**Memory (RAM):**
```
Minimum: 8192 MB (8 GB)
Recommended: 12288 MB (12 GB) if host has 16GB+
```

**Hard disk:**
```
☑ Create a virtual hard disk now
Click "Create"
```

**Disk settings:**
```
File size: 50 GB minimum (80 GB recommended)
Hard disk file type: VDI (VirtualBox Disk Image)
Storage: Dynamically allocated
```

Click "Create"

---

### Step 4: Configure VM Settings

**Before starting VM, adjust settings:**

Right-click VM → Settings

**System:**
```
Motherboard tab:
  Base Memory: 8192 MB (or more)
  Boot Order: Hard Disk first, Optical second

Processor tab:
  Processors: 4 CPUs minimum (6-8 if available)
  ☑ Enable PAE/NX
```

**Display:**
```
Screen tab:
  Video Memory: 128 MB (maximum)
  ☑ Enable 3D Acceleration
```

**Storage:**
```
Click "Empty" under Controller: IDE
Click disk icon on right → "Choose a disk file"
Select downloaded Ubuntu ISO
```

**Network:**
```
Adapter 1:
  ☑ Enable Network Adapter
  Attached to: NAT (or Bridged Adapter for better performance)
```

Click "OK"

---

### Step 5: Install Ubuntu

**Start VM:**

- Select VM → Click "Start"
- VM boots from Ubuntu ISO

**Ubuntu installer:**

1. **Language:** Select English (or your language)
2. **Install Ubuntu:** Click "Install Ubuntu"
3. **Keyboard layout:** Select your layout
4. **Updates:** 

   - ☑ Normal installation
   - ☑ Download updates while installing
   - ☑ Install third-party software

5. **Installation type:** 
   - ☑ Erase disk and install Ubuntu (safe - only affects VM disk)
6. **Time zone:** Select your location
7. **User setup:**

   - Your name: (your name)
   - Computer name: simtofly-vm
   - Username: (your username)
   - Password: (create strong password)
   - ☑ Require password to log in

**Installation takes:** 15-30 minutes

**Restart when prompted**

---

### Step 6: Install Guest Additions

**After Ubuntu boots:**

VirtualBox menu → Devices → Insert Guest Additions CD

**In Ubuntu terminal:**
```bash
sudo apt update
sudo apt install build-essential dkms linux-headers-$(uname -r)
sudo mkdir /media/cdrom
sudo mount /dev/cdrom /media/cdrom
cd /media/cdrom
sudo ./VBoxLinuxAdditions.run
```

**Reboot:**
```bash
sudo reboot
```

**Benefits:**

- Better screen resolution
- Shared clipboard
- Drag and drop files
- Better mouse integration

---

### Step 7: Take Snapshot

**Before starting tutorials:**

VM menu → Machine → Take Snapshot
```
Name: Fresh Ubuntu Install
Description: Clean Ubuntu 22.04 before SimToFly setup
```

**Why?** If something breaks, restore to this point.

---

### VM Performance Tips

**If VM is slow:**

1. **Allocate more resources:**

   - More RAM (if host allows)
   - More CPU cores
   - More video memory

2. **Enable 3D acceleration:**

   - Settings → Display → Enable 3D Acceleration

3. **Use SSD for VM:**

   - Store VM on SSD, not HDD

4. **Close other applications:**

   - On host OS while running VM

5. **Disable visual effects in Ubuntu:**
```bash
   sudo apt install gnome-tweaks
   gnome-tweaks
   # Disable animations
```

---

## Dual Boot Installation

**Best for:** Users wanting better performance while keeping current OS

**Pros:**

- Full hardware performance
- Native GPU acceleration
- Better Gazebo performance
- Keep existing OS

**Cons:**
- Requires disk partitioning (some risk)
- More complex setup

**⚠️ Warning:** Back up important data before proceeding!

---

### Prerequisites

**Before starting:**

- [ ] Back up all important data
- [ ] 50GB+ free disk space
- [ ] USB drive (8GB+)
- [ ] Stable power (laptop: plug in charger)
- [ ] BIOS/UEFI access knowledge

---

### Step 1: Create Ubuntu USB

**On Windows:**

1. Download Rufus: https://rufus.ie/
2. Insert USB drive (will be erased!)
3. Open Rufus
4. Select your USB drive
5. Select Ubuntu ISO
6. Click "Start"
7. Wait for completion (~5-10 minutes)

**On macOS/Linux:**

1. Download Etcher: https://etcher.balena.io/
2. Insert USB drive
3. Select Ubuntu ISO
4. Select USB drive
5. Flash!

---

### Step 2: Free Up Disk Space

**Windows:**

1. Open "Disk Management" (search in Start menu)
2. Right-click your largest partition (usually C:)
3. Select "Shrink Volume"
4. Shrink by: 50000 MB (50 GB) or more
5. Click "Shrink"
6. Should see "Unallocated" space

**macOS:**

1. Open "Disk Utility"
2. Select main disk
3. Click "Partition"
4. Add partition: 50GB+ for Ubuntu
5. Format: Free Space
6. Apply

---

### Step 3: Boot from USB

**Enter BIOS/UEFI:**

- Restart computer
- Press key during startup:
  - Dell/HP: F2 or F12
  - Lenovo: F1 or F2
  - ASUS: F2 or Del
  - Acer: F2 or Del

**Change boot order:**

1. Find "Boot" menu
2. Move USB drive to top
3. Save and exit (usually F10)

**Computer boots from USB:**

- Shows Ubuntu logo
- Select "Try or Install Ubuntu"

---

### Step 4: Install Ubuntu

**Important:** Choose "Install Ubuntu alongside [Windows/macOS]"

**Installation steps:**

1. **Language:** English
2. **Install Ubuntu:** Click Install
3. **Keyboard:** Select layout
4. **Updates:** 

   - Normal installation
   - Download updates
   - Install third-party software
5. **Installation type:**

   - **☑ Install Ubuntu alongside [your OS]** ← Important!
   - Ubuntu will use free space created earlier
6. **Review partition changes**
7. **Time zone:** Select location
8. **User setup:**

   - Name, username, password
   - Computer name: simtofly

**Installation:** 15-30 minutes

**Restart when complete**

---

### Step 5: Configure Bootloader

**After reboot:**

- Should see GRUB menu
- Options: Ubuntu, Windows (or macOS)
- Default: Ubuntu

**To change default OS:**
```bash
sudo nano /etc/default/grub
```

Change:
```
GRUB_DEFAULT=0    # Ubuntu
# or
GRUB_DEFAULT=2    # Windows (usually)
```

Update:
```bash
sudo update-grub
```

---

### Step 6: Verify Both OS Work

**Test Ubuntu:**

- Boot into Ubuntu
- Verify everything works

**Test other OS:**

- Reboot → Select Windows/macOS from GRUB
- Verify it still works

✅ **Both work?** Dual boot successful!

---

### Dual Boot Tips

**Switch between OS:**

- Restart → Choose from GRUB menu
- Default selection after 10 seconds

**If GRUB doesn't show:**
```bash
# In Ubuntu:
sudo update-grub
```

**If Windows doesn't appear:**
```bash
# In Ubuntu:
sudo os-prober
sudo update-grub
```

---

## Native Installation

**Best for:** Dedicated machine for drone development, best performance

**Pros:**

- Maximum performance
- Full hardware access
- No compromises
- Best for serious development

**Cons:**

- Erases existing OS
- Requires dedicated hardware

**Use this if:**

- You have spare computer
- You don't need Windows/macOS on this machine
- You want best performance

---

### Installation Steps

**Same as dual-boot, but:**

**At "Installation type":**

- **Choose:** "Erase disk and install Ubuntu"
- **Warning:** This deletes everything on disk!

**Make absolutely sure:**

- You backed up important data
- You selected correct disk (if multiple disks)
- You're okay losing current OS

**Otherwise:** Same as dual-boot installation above

---

## ✅ Verify Installation

After installing Ubuntu (any method), verify:

**Ubuntu version:**
```bash
lsb_release -a
```
Should show: Ubuntu 22.04.x LTS

**System resources:**
```bash
# RAM
free -h

# CPU
lscpu | grep "CPU(s)"

# Disk space
df -h /
```

**Internet:**
```bash
ping -c 3 google.com
```

**Graphics (if VM):**
```bash
glxinfo | grep "OpenGL"
```

All working? ✅ Ready for [Phase 1!](../phase-1-simulation/1.1-prerequisites.md)

---

## Common Issues

### VirtualBox: "VT-x is not available"

**Cause:** Virtualization disabled in BIOS

**Solution:**

1. Restart computer → Enter BIOS
2. Find "Virtualization Technology" or "VT-x" or "AMD-V"
3. Enable it
4. Save and exit BIOS
5. Try VirtualBox again

---

### Dual Boot: GRUB not showing

**Cause:** GRUB didn't install properly

**Solution:**
Boot Ubuntu USB → Try Ubuntu → Open terminal:
```bash
sudo add-apt-repository ppa:yannubuntu/boot-repair
sudo apt update
sudo apt install boot-repair
boot-repair
```
Follow prompts.

---

### Dual Boot: Windows won't boot

**Cause:** GRUB installed over Windows bootloader

**Solution:**

1. Use Boot Repair (above)
2. Or: Boot from Windows recovery USB
3. Run: `bootrec /fixmbr` and `bootrec /fixboot`
4. Reinstall GRUB from Ubuntu live USB

---

### Screen resolution wrong in VM

**Cause:** Guest Additions not installed

**Solution:**
Install Guest Additions (see VM Step 6 above)

---

### Ubuntu installer crashes

**Cause:** Bad ISO or USB

**Solution:**

1. Verify ISO checksum
2. Re-download ISO
3. Re-flash USB drive
4. Try different USB drive

---

## Additional Resources

**Official Ubuntu Guides:**

- Installation: https://ubuntu.com/tutorials/install-ubuntu-desktop
- Dual boot Windows: https://help.ubuntu.com/community/WindowsDualBoot
- VirtualBox: https://www.virtualbox.org/manual/

**Video Tutorials:**

- Search YouTube: "Install Ubuntu 22.04"
- Filter: Last year

**Community Help:**

- Ubuntu Forums: https://ubuntuforums.org/
- Ask Ubuntu: https://askubuntu.com/

---

## Quick Decision Guide

**Choose installation method:**

```
Do you have spare computer?
  YES → Native installation (best performance)
  NO ↓

Are you comfortable with disk partitioning?
  YES → Dual boot (good performance + keep current OS)
  NO ↓

Is your computer powerful? (16GB+ RAM, 8+ cores)
  YES → Virtual Machine (safe + easy)
  NO → Consider dual boot or upgrade hardware
```

---

[← Back to Prerequisites](../phase-1-simulation/1.1-prerequisites.md) | [Continue to 1.2 Environment Setup →](../phase-1-simulation/1.2-environment-setup.md)
