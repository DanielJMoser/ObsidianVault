# Expanding Root Partition - Complete Implementation Guide

**Date:** 2025-10-30
**System:** Arch Linux on /dev/nvme0n1
**Goal:** Free up 100+ GB on root partition by moving /home to new partition

---

## Executive Summary

**Problem:** Root partition (/dev/nvme0n1p5) is 77% full (151GB/206GB) with only 45GB free.

**Solution:** Create new 250GB partition from 387GB free space and move /home directory to it.

**Expected Result:** Root partition will have ~168GB free (123GB freed from /home migration).

**Risk Level:** LOW - Non-destructive operation, fully reversible.

---

## Current Disk Layout

```
/dev/nvme0n1 (931.51 GB NVMe SSD)

Number  Start   End     Size    Type         Filesystem    Mount     Purpose
─────────────────────────────────────────────────────────────────────────────
        17.4kB  1049kB  1031kB  Free Space
 1      1049kB  524MB   523MB   Primary      fat32         -         Windows EFI
 2      524MB   659MB   134MB   Primary      -             -         MS Reserved
 3      659MB   352GB   351GB   Primary      ntfs          -         Windows System
        352GB   739GB   387GB   FREE SPACE ← TARGET
 4      739GB   740GB   1074MB  Primary      fat32         /boot     Linux EFI
 5      740GB   965GB   225GB   Primary      ext4          /         Linux Root
 7      965GB   990GB   25.1GB  Primary      linux-swap    [SWAP]    Swap
 6      990GB   1000GB  9997MB  Primary      ntfs          -         Win Recovery
        1000GB  1000GB  729kB   Free Space
```

**Note:** Partition 5 comes before partition 7 in creation order, hence the numbering.

---

## Disk Usage Analysis

### Root Partition Usage
- **Total:** 206 GB
- **Used:** 151 GB (77%)
- **Available:** 45 GB (23%)

### /home Directory Breakdown
**Total: 123 GB** (81% of root usage)

| Directory | Size | Purpose |
|-----------|------|---------|
| `.npm` | 24 GB | Node package manager cache |
| `.cache` | 18 GB | Application caches |
| `Android` | 18 GB | Android SDK |
| `.local` | 13 GB | Local application data |
| `.lmstudio` | 13 GB | AI model files |
| `.gradle` | 7.8 GB | Gradle build cache |
| `WebstormProjects` | 7.3 GB | JavaScript projects |
| `IdeaProjects` | 4.3 GB | Java projects |
| `.cargo` | 3.8 GB | Rust toolchain cache |
| `.rustup` | 2.5 GB | Rust version manager |
| `qmk_firmware` | 2.2 GB | Keyboard firmware |
| Other | ~8 GB | Various config and data |

---

## Implementation Plan

### Strategy: Create New Partition + Move /home


**Why this approach:**
1. **Zero risk** - No partition resizing or moving
2. **Reversible** - Can undo if needed
3. **No downtime** - Done while system running
4. **Best practice** - Separate /home is standard Linux architecture
5. **Respects dual-boot** - Windows partitions untouched

**New Partition Specifications:**
- **Size:** 250 GB (from 387 GB free space)
- **Location:** Start at 352GB, end at 602GB
- **Filesystem:** ext4
- **Label:** home-data
- **Mount point:** /home
- **Remaining free space:** 137 GB (for future use)

---

## Step-by-Step Implementation

### Prerequisites

Before starting:
- [ ] Close all applications
- [ ] Ensure no critical work in progress
- [ ] Have recovery USB ready (optional but recommended)
- [ ] Estimated time: 30-60 minutes

---

### Step 1: Verify Current Partition Layout

```bash
sudo parted /dev/nvme0n1 unit GB print free
```

**Expected output:** Shows 387GB free space between partitions 3 and 4.

✅ **Verification:** Free space confirmed from 352GB to 739GB.

---

### Step 2: Create New Partition

```bash
# Launch parted interactive mode
sudo parted /dev/nvme0n1
```

**Inside parted, run these commands:**

```parted
print free                                    # Confirm free space
mkpart primary ext4 352GB 602GB              # Create 250GB partition
print                                         # Verify partition 8 created
quit
```

**Important Notes:**
- The partition will be created as **/dev/nvme0n1p8**
- Start: **352GB** (right after Windows partition 3)
- End: **602GB** (250GB size)
- This leaves **137GB** free space (602GB to 739GB)

✅ **Verification:** Run `lsblk` to confirm /dev/nvme0n1p8 exists.

```bash
lsblk /dev/nvme0n1
```

Expected output should show nvme0n1p8.

---

### Step 3: Format the New Partition

```bash
# Format as ext4 with descriptive label
sudo mkfs.ext4 -L home-data /dev/nvme0n1p8
```

**Get the UUID for later use:**

```bash
sudo blkid /dev/nvme0n1p8
```

**Example output:**
```
/dev/nvme0n1p8: LABEL="home-data" UUID="67093d5-0410-4633-921d-86a58040d9b5" TYPE="ext4"
```

**⚠️ IMPORTANT:** Copy the UUID value - you'll need it for /etc/fstab!

✅ **Verification:** Partition formatted successfully with ext4 filesystem.

---

### Step 4: Mount New Partition Temporarily

```bash
# Create temporary mount point
sudo mkdir -p /mnt/new-home

# Mount the new partition
sudo mount /dev/nvme0n1p8 /mnt/new-home

# Verify it's mounted and accessible
df -h /mnt/new-home
ls -la /mnt/new-home  # Should be empty except lost+found
```

✅ **Verification:** Shows partition mounted with ~246GB available.

---

### Step 5: Copy /home Data to New Partition

This step copies all your user data to the new partition while preserving all permissions, timestamps, and attributes.

```bash
# Use rsync for safe, verifiable copy
# -a: archive mode (preserves everything)
# -x: don't cross filesystem boundaries
# -H: preserve hard links
# -A: preserve ACLs
# -W: copy whole files (faster on local disk)
# -X: preserve extended attributes
# -S: handle sparse files efficiently
# --numeric-ids: preserve UID/GID numbers
# --info=progress2: show overall progress

sudo rsync -axHAWXS --numeric-ids --info=progress2 /home/ /mnt/new-home/
```

**Expected duration:** 15-30 minutes depending on disk speed.

**You'll see output like:**
```
     12.34G  45%   123.45MB/s    0:08:32 (xfr#1234, to-chk=5678/9012)
```

**After completion, verify the copy:**

```bash
# Compare sizes
du -sh /home
du -sh /mnt/new-home

# Should show identical or near-identical sizes (123GB)

# Verify file count
find /home -type f | wc -l
find /mnt/new-home -type f | wc -l

# Spot check some important directories
ls -la /mnt/new-home/danielm/
ls -la /mnt/new-home/danielm/WebstormProjects/
```

✅ **Verification:** Sizes match, file counts match, directory structure intact.

---

### Step 6: Backup and Update /etc/fstab

**First, create a backup:**

```bash
sudo cp /etc/fstab /etc/fstab.backup
```

**View current fstab:**

```bash
cat /etc/fstab
```

**Current fstab content:**
```
UUID=f5f5d80e-fb1a-47e6-be56-57fa89aa8640  /       ext4  rw,relatime  0 1
UUID=FD36-F882                             /boot   vfat  rw,relatime  0 2
UUID=5868d1d0-cf27-498f-afc3-4aa32652d06f  none    swap  defaults     0 0
```

**Edit fstab:**

```bash
sudo nano /etc/fstab
```

**Add this line** (replace with your actual UUID from Step 3):

```
UUID=your-actual-uuid-from-step3  /home   ext4    rw,relatime  0 2
```

**Complete fstab should look like:**
```
UUID=f5f5d80e-fb1a-47e6-be56-57fa89aa8640  /       ext4  rw,relatime  0 1
UUID=FD36-F882                             /boot   vfat  rw,relatime  0 2
UUID=5868d1d0-cf27-498f-afc3-4aa32652d06f  none    swap  defaults     0 0
UUID=your-actual-uuid-from-step3           /home   ext4  rw,relatime  0 2
```

Save and exit (Ctrl+X, Y, Enter in nano).

✅ **Verification:** Backup created at /etc/fstab.backup.

---

### Step 7: Test Mount Without Rebooting

This is a critical safety step - test everything before rebooting!

```bash
# Unmount the temporary mount
sudo umount /mnt/new-home

# Rename current /home temporarily (don't delete yet!)
sudo mv /home /home.old

# Create new empty /home directory
sudo mkdir /home

# Test mounting from fstab
sudo mount -a

# Check if /home is now mounted from new partition
df -h /home
```

**Expected output:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p8  246G  123G  111G  53% /home
```

**Verify you can access your files:**

```bash
ls -la /home/danielm/
ls -la ~/WebstormProjects/
ls -la ~/IdeaProjects/
```

**Check root partition space (old /home still there as /home.old):**

```bash
df -h /
```

Should still show 77% used since we haven't deleted /home.old yet.

✅ **Verification:** New /home mounted successfully, all files accessible.

---

### Step 8: Reboot and Final Verification

If Step 7 looks good, proceed with reboot:

```bash
sudo reboot
```

**After reboot, verify everything:**

```bash
# 1. Check /home is mounted from new partition
df -h /home
mount | grep /home

# Expected:
# /dev/nvme0n1p8 on /home type ext4 (rw,relatime)

# 2. Verify you can access your files
ls -la ~/
cd ~/WebstormProjects/
cd ~/IdeaProjects/

# 3. Test applications
# - Open WebStorm or VSCode
# - Open a project
# - Verify git works
# - Check that npm/gradle work

# 4. Check overall system
lsblk
df -h
```

✅ **Verification:** System boots normally, /home mounted, all applications work.

---

### Step 9: Clean Up Old /home Data

**⚠️ ONLY proceed if Step 8 verification is completely successful!**

**Double-check everything works:**
- Applications load
- Projects open
- Git repositories accessible
- Development tools function normally
- No error messages

**If everything is perfect, clean up:**

```bash
# Check current root partition usage
df -h /

# Should show ~77% used (151GB), including /home.old

# Remove old home directory
sudo rm -rf /home.old

# This may take a few minutes

# Check new free space on root
df -h /
```

**Expected result:**
```
Filesystem      Size  Used Avail Use% Mounted on
/dev/nvme0n1p5  206G   28G  168G  15% /
```

🎉 **Success!** Root partition now has **168GB free** (up from 45GB).

---

## Verification Checklist

After completion, verify:

- [ ] /home is mounted from /dev/nvme0n1p8
- [ ] df -h shows ~168GB free on root partition
- [ ] All files in ~/ are accessible
- [ ] WebStorm projects open correctly
- [ ] IntelliJ projects open correctly
- [ ] Git repositories work
- [ ] npm/node projects function
- [ ] Android SDK accessible
- [ ] No error messages in system logs
- [ ] No application crashes
- [ ] User permissions intact (files owned by danielm)

---

## Rollback Plan

If something goes wrong before deleting /home.old:

### Option 1: Before Reboot (if mount test fails)

```bash
# Unmount new /home
sudo umount /home

# Restore old /home
sudo rmdir /home
sudo mv /home.old /home

# Remove fstab entry
sudo nano /etc/fstab  # Delete the /home line

# Reboot
sudo reboot
```

### Option 2: After Reboot (if issues discovered)

```bash
# Boot into recovery mode or live USB

# Mount root partition
sudo mount /dev/nvme0n1p5 /mnt

# Edit fstab to remove /home entry
sudo nano /mnt/etc/fstab  # Remove /home line

# Restore old /home
sudo mv /mnt/home.old /mnt/home

# Unmount and reboot
sudo umount /mnt
sudo reboot
```

### Option 3: Complete Rollback

```bash
# If you want to completely undo everything:

# 1. Restore old /home (as above)

# 2. Delete the new partition
sudo parted /dev/nvme0n1
rm 8  # Remove partition 8
quit

# This returns the 250GB to free space
```

---

## Expected Results Summary

### Before
- Root partition: 206GB total, 151GB used, 45GB free (77% full)
- /home: Part of root partition (123GB)
- Free disk space: 387GB unallocated

### After
- Root partition: 206GB total, 28GB used, 168GB free (15% full)
- /home: Separate 250GB partition, 123GB used, 111GB free (53% full)
- Free disk space: 137GB unallocated (for future use)

### Benefits
- ✅ Root partition freed: **+123GB** (45GB → 168GB)
- ✅ Goal exceeded: 123GB freed (goal was 100GB+)
- ✅ Clean architecture: Separate /home follows best practices
- ✅ Windows untouched: Dual-boot preserved
- ✅ Future flexibility: 137GB remaining for other needs
- ✅ Easy backups: Can backup /home partition independently
- ✅ System upgrades: Can reinstall OS without losing user data

---

## Maintenance Notes

### Future Considerations

**Remaining 137GB free space can be used for:**
- Expanding /home if needed in future (extend p8)
- Creating separate /var partition
- Adding docker/container storage partition
- Expanding swap if running memory-intensive workloads
- Creating backup partition

**To expand /home partition later:**
```bash
# Boot from live USB
sudo parted /dev/nvme0n1
resizepart 8 739GB  # Extend to use all free space before p4
quit

# Resize filesystem
sudo e2fsck -f /dev/nvme0n1p8
sudo resize2fs /dev/nvme0n1p8
```

### Cache Cleanup (Optional)

After migration, consider cleaning caches to free even more space:

```bash
# NPM cache (safe to delete, will regenerate)
npm cache clean --force
# Frees ~24GB

# Gradle cache (can be regenerated)
rm -rf ~/.gradle/caches
# Frees ~7.8GB

# General system cache
rm -rf ~/.cache/*
# Frees ~18GB

# Docker (if installed)
docker system prune -a
```

These will regenerate as needed and could temporarily free ~50GB more.

---

## Technical Details

### Why This Approach is Safe

1. **Non-destructive:** No existing partitions are modified
2. **Reversible:** Old data kept until verified
3. **Incremental:** Test before committing
4. **Filesystem-safe:** rsync preserves all attributes
5. **Boot-safe:** fstab tested before reboot
6. **Recovery-friendly:** Can boot from USB if needed

### Alternative Approaches Considered

**Option A: Move partitions** ❌
- Move p6 and p7 to end of disk
- Expand p5 into freed space
- **Rejected:** High risk, long duration, requires live USB

**Option B: Delete swap, expand root** ❌
- Only gains 25GB
- Still doesn't meet 100GB goal
- **Rejected:** Insufficient space gained

**Option C: Use LVM** ❌
- Would require converting to LVM
- Complex migration, high risk
- **Rejected:** Unnecessary complexity

**Option D: New partition + move /home** ✅
- **Selected:** Safe, effective, follows best practices

---

## References

### Useful Commands

```bash
# Disk information
lsblk
df -h
sudo fdisk -l
sudo parted /dev/nvme0n1 print free

# Partition UUIDs
sudo blkid

# Disk usage analysis
du -sh /home/*
du -h --max-depth=1 / | sort -hr

# Filesystem check
sudo e2fsck -f /dev/nvme0n1p8

# Mount management
mount | grep home
sudo mount -a

# System logs
journalctl -b
dmesg | grep -i error
```

### Documentation
- Arch Wiki: Partitioning
- Arch Wiki: fstab
- rsync man page: `man rsync`
- parted documentation: `info parted`

---

## Notes

**Created:** 2025-10-30
**System:** Arch Linux 6.17.5-arch1-1
**Disk:** Samsung NVMe 1TB (nvme0n1)
**User:** danielm

**Status:** 📋 Documentation complete, ready for implementation

**Last Updated:** 2025-10-30

---

## Execution Log

Use this section to track your progress:

```
[ ] Step 1: Partition layout verified
[ ] Step 2: Partition 8 created (352GB-602GB)
[ ] Step 3: Formatted as ext4, UUID: _______________
[ ] Step 4: Mounted at /mnt/new-home
[ ] Step 5: Data copied with rsync (Duration: ___ mins)
[ ] Step 6: /etc/fstab updated and backed up
[ ] Step 7: Test mount successful, files accessible
[ ] Step 8: Rebooted, /home mounted from p8
[ ] Step 9: /home.old deleted, 168GB free confirmed

Completion Date: _______________
Final Root Space: _______________
```
