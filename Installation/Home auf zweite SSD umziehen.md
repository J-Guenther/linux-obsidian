### 1. Prepare the 1TB SSD

- **Format it** (if it's not already) — use something like `ext4` format.
	- You can do this with _Disks_ (`gnome-disks`) or `gparted`.
- **Create a mount point** — a folder where it will be mounted automatically at boot.

Mount point:
```bash
sudo mkdir /mnt/data
```
(later you’ll make `/mnt/data` your `/home`!)

### 2. Copy your `/home` folder

Copy the existing `/home` to the 1TB SSD:

```bash
sudo rsync -aAXv /home/ /mnt/data/home/
```
(`rsync` is safer than `cp` because it preserves permissions, symlinks, etc.)


### 3. Mount the 1TB drive at `/home`

Edit your `/etc/fstab` to mount the 1TB drive automatically at `/home`.

First, find your 1TB drive’s UUID:
```bash
sudo blkid
```
Then edit fstab:
```bash
sudo nano /etc/fstab
```
Add a line at the bottom:
```
UUID=1234-5678-90AB-CDEF /home ext4 defaults 0 2
```
### 4. Final steps
**Move the original `/home` away** (just rename it for backup):
```bash
sudo mv /home /home_backup
```
Mount everything (-a applies the latest changes)
```bash
sudo mount -a
```
**Check that your home is correctly mounted**:
```bash
df -h
```
Your `/home` should now point to the SSD you chose!

### Las Step: Move hold Home to the new Home
You have your original files in `/home_backup` (remember, we renamed the old one).

You now just need to copy your real home folders into the new `/home`:
```bash
sudo rsync -aAXv /home_backup/ /home/
```
(**Be very careful with the slashes — notice it's `/home_backup/` → `/home/`**)

This will:
- Copy everything back into `/home`
- Preserve permissions, ownership, etc.
- Move all your user accounts and settings