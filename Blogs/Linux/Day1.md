# Introduction to Linux

Despite what is commonly believed, Linux is technically a **Kernel**.

A kernel is the core component of an operating system that acts as a bridge between hardware and software.

The term **Linux** is often used colloquially to refer to a complete operating system, which is technically incorrect. A complete OS not only includes Kernel but also various libraries, user interfaces, and other system tools.

A **Linux Distribution** (or *Distro* for short), on other hand is a complete operating system that combines the Linux kernel with additional tools and utilities. Examples include **Red Hat**, **Ubuntu**, and **Debian**.

---

## Linux Distribution Families

Linux distributions are grouped into *Families* based on their **base system**.
These includes:
- **Debian-based**: Stability, vast software repositories, strong community.

- **RHEL-based**: Enterprise-grade, long-term support, security compliance.

- **Arch-based**: Cutting-edge, rolling updates, high customization.

- **SUSE-based**: Powerful admin tools, choice of stable or rolling releases.

- **Independent**: Unique approaches, specialized use cases.
---
# Linux File System

Navigating files in Linux can be a hassle, so let's summarize each folder in the root directory.

Use the **cd** command tp navigate through directories.

Use the **ls** command is used to list all files in the current directory.

- **/bin** : Contains essential user Binaries (Available to user).
- **/sbin** : Contains System Binaries (intended for sudo and root user).
- **/lib** : Stores shared libraries required by binaries in `/bin` & `/sbin`.
- **/usr** : Contains user related libraries, programs.
- **/etc** : Stands for "Editable Text Config; contains system configuration files.
- **/home** : Stores User Data and personal directories.
- **/boot** : Contain files required to boot system.
- **/dev** : Contains device files of various drivers.
- **/opt** : Optional file directory or for third party softwares..
- **/var** : Contains variable files such as logs, caches ,etc.
- **/tmp** : stores temporary file.
- **/proc** : A virtual filesystem created by kernel to keep track of running softwares.