# Proxmox Configuration

reference: https://pve.proxmox.com/pve-docs/chapter-sysadmin.html

## Repository Config Changes

APT Repositories are defined in the file /etc/apt/sources.list and in .list files placed in /etc/apt/sources.list.d/.

Use the *Proxmox VE No-Subscription* repositories instead of the *Proxmox VE Subscription* repositories.

**Step 1:**

Use this config code:

File /etc/apt/sources.list

> deb http://ftp.debian.org/debian bookworm main contrib

> deb http://ftp.debian.org/debian bookworm-updates main contrib

> \# Proxmox VE pve-no-subscription repository provided by proxmox.com,

> \# NOT recommended for production use

> deb http://download.proxmox.com/debian/pve bookworm pve-no-subscription

> \# security updates

> deb http://security.debian.org/debian-security bookworm-security main contrib'

**Step 2:**

Comment out this code in
File /etc/apt/sources.list.d/pve-enterprise.list

> \# deb https://enterprise.proxmox.com/debian/pve bookworm pve-enterprise
