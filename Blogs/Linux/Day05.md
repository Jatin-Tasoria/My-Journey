# Storage Management

## Disk Partition
Before modifying storage, it is necessary to understand how linux sees the disks

**Key Concepts**
- Disks: Physical devices. Eg: `/dev/sda`
- Partition: Logical division of disks. Eg: `/dev/sda1`
- Filesystems: ext4,xfs, etc

---

## Useful Commands
- lsblk : list disks and partition
- blkid : Show UUids and filesystem types
- df -h : Disk usage
- fdisk - l : Detailed partition info
- mount : list all devices mounted to system.

---

## Creating and managing partition
> Before proceeding, perform these actions on a empty flash drive.
> /dev/sdb is name of flash drive on my system

Steps:
```bash
fdisk /dev/sdb
```
- Create a new partition
- Write change to disk. (Permanent changes)

**Formatting the partition**
```bash
mkfs.ext4 /dev/sdb
```
**Verification**
```bash
blkid /dev/sdb1
```

---

## Mounting & Persistent storage
Mounting allows linux to use the storage device.

- **Temporary Mount**
```bash
mount /dev/sdb /media/data
```

- **Permanent Mount**
  1. Find Uuids
```bash
blkid
```
  2. Edit /etc/fstab
> Be careful while editing it, if you make a mistake the system might not boot.
```bash
UUID=xxx /mnt/data ext4 default 0 0  
```

---

## LVM (Logical Virtual Manager)
Allows the creation of groups of disks or partitions that can be assemble into single or multiple filesystems.
Provides flexible file storage.

>To install LVM run these following command
>For rhel :sudo dnf install -y lvm2
>For ubuntu : sudo 

### Component
- PV (Physical Volume)
- VG (Volume Group)
- LV (Logical Volume)

### Commands
- pvs : Lists physical volumes
- vgs : Lists Volume groups
- lvs : Lists Logical volume
- pvdisplay : Displays info about physical volume
- vgdisplay : Displays info about volume groups
- lvdisplay : Displays info about logical volume
- pvcreate /dev/sdc : Creates a new physical volume
- vgcreate myvg /dev/sdc : Creates new Volume group
- lvcreate -L 2G -n mylv myvg : Creates new Logical volume on top of the volume group

**Format & Mount**
- mkfs.xfs /dev/myvg/mylv
- mount /dev/myvg/mylv /data

---

## Extending Logical volume

### Commands
**Create Volumes**
- vgextend <groupname> /dev/sdc : To add new drive/ partition to volume group
- lvextend -L 10G /dev/< label of volume you want to extend > 

**Resize filesystem**
- For xfs
  - xfs_growfs /data

- For ext4
  - resize2fs /dev/myvg/mylv

---