# Proxmox helper utility script (pve-utils)

## ⚠️WARNING: This utility is currently under heavy development, most of the feature may not be available.

![alt proxmox logo](https://upload.wikimedia.org/wikipedia/en/thumb/2/25/Proxmox-VE-logo.svg/500px-Proxmox-VE-logo.svg.png)

### pve-utils is a utility helper script for setting up Proxmox, deploying VM, LXC, VFIO, etc.

![alt pve-utils screenshot](https://i.imgur.com/6I3FHSw.png)

# Quick Start Setup

### ⚠️ Quick Start Setup MUST be done on a clean install of Proxmox, using it on a non-clean system may break your system.

## 1. Setup as a Server / NAS

Run the following command in your Proxmox VE host shell (terminal or SSH):
```
bash <(curl -fsSL https://raw.githubusercontent.com/kwankiu/pve-utils/main/pve-utils) --quickstartserver
```

### Here are some examples on what you can run:
- Smart Home : [Home Assistant](https://www.home-assistant.io/)
- Web Services & Containers : [Portainer](https://www.portainer.io/)/[Docker](https://docker.io), Dockge, Umbrel, CasaOS, Runtipi, Podman, etc.
- NAS Storage : [TrueNAS Scale/Core](https://www.truenas.com/), [OpenMediaVault](https://www.openmediavault.org/), [Xpenology (DSM7)](https://xpenology.org/), [UnRAID](https://unraid.net/), etc.
- Router & Networking : [OpenWRT](https://openwrt.org/), [Cloudflared](https://github.com/cloudflare/cloudflared), [Nginx Proxy Manager](https://nginxproxymanager.com/), [Wireguard](https://www.wireguard.com/), [YunoHost](https://yunohost.org/), [iStoreOS](https://www.istoreos.com/), [Pi-hole](https://pi-hole.net/), [AdGuard Home](https://github.com/AdguardTeam/AdguardHome), etc.
- Deploying Linux/Unix Server (Ubuntu, Debian, Arch Linux, CentOS, FreeBSD, etc) images (LXC or VM)

⚠️ To be written

## 2. Setup as a Gaming / Media HomeLab

Run the following command in your Proxmox VE host shell (terminal or SSH):
```
bash <(curl -fsSL https://raw.githubusercontent.com/kwankiu/pve-utils/main/pve-utils) --quickstartgaming
```

### Here are some examples on what you can run:
 - ***Everything from above (1. Setup as a Server / NAS) and***
 - Windows 10/11 Gaming VM
 - [HoloISO](https://github.com/HoloISO/holoiso) (SteamOS) Linux Gaming VM
 - Linux Desktop VM (Ubuntu, Debian, Arch Linux, CentOS, FreeBSD, NixOS, Linux Mint, etc)
 - Hackintosh (macOS VM)
 - ***With GPU Support (GPU Passthrough)***
 
⚠️ To be written

## 3. Run Post Install Setup Only

#### This option is currently identical to running the Proxmox VE Post Install from https://tteck.github.io/Proxmox/.

Run the following command in your Proxmox VE host shell (terminal or SSH):
```
bash <(curl -fsSL https://raw.githubusercontent.com/kwankiu/pve-utils/main/pve-utils) --postinstallonly
```
# Installation

The Proxmox Helper Utility (pve-utils) should be already installed automatically if you setup your Proxmox VE from any Quick Start Setup options above.

If you want to use this utility without using Quick Start Setup, it can be installed by running :

```
bash <(curl -fsSL https://raw.githubusercontent.com/kwankiu/pve-utils/main/pve-utils) --install
```

# Usage
```
pve-utils <options> --ARGUMENTS=<value> or -FLAGS
```

## Options

#### Utility
| Options | Arguments | Description |
| ------------- | ------------- | ------------- |
| `-h` or `--help` | N/A | Usage and Infomation of this Utility. |
| `-d` or `--dev` | N/A | Use latest dev version of this Utility. |
| `-i` or `--install` | `<channel>` | Install latest utility to PATH (/usr/bin). install channel options: main, dev. |

#### Create VM / LXC
| Options | Arguments / Flags | Description |
| ------------- | ------------- | ------------- |
| `create` |  no args specified | Show create VM/LXC utility menu. |
| `create` |  `--name` | Set VM/LXC Name. |
| `create` |  `--id` | Set VM/LXC ID. |
| `create` |  `--node` | Set which Node to create VM/LXC on. |
| `create` |  `--os` | Set VM Operating System Type (`linux`,`win10`,`win11`,`win`,`macOS`,`other`). |
| `create` |  `--osiso` | Attach an OS Installation ISO (`auto` or `<file_path>`). |
| `create` |  `--cpu` | Set VM CPU Model (`host` or ``). |
| `create` |  `--vcpu` | Set number of vCPU/Threads (`max` or `<number>`). |
| `create` |  `-cpupinning` or `--cpupinning` | Pin vCPUs to CPU Threads (`auto` will pin from the 2nd cpu core or `<threads_number1,2,3>` for manual pinning: `--cpupinning=2,3,4,5,6,7,8,9`). |
| `create` |  `--memory` | Set VM Memory (`max` or `<size>`). |
| `create` |  `-balloon` | Enable VM Memory Ballooning. |
| `create` |  `--disk` | Attach or Create a VM Storage Disk. (Usage: `--disk=SATA,/dev/lvm/vm-disk-100,cache=none`) |
| `create` |  `-startatboot` | Automatically Start VM/LXC on boot. |
| `create` |  `-hidevm` or `--hidevm` | Hide VM Status Guest (optional values are `full`,`hypervisoroff`). |
| `create` |  `--smbios` | Pass SMBIOS Information (`host`,`opencore`,`custom`). |

⚠️ To be written, as of now ***none of the above arguments*** are implemented yet.

## Additional Infomation

#### Using the dev branch version
#### (WARNING: dev branch are not tested and may be broken.)
```
bash <(curl -fsSL https://raw.githubusercontent.com/kwankiu/pve-utils/main/pve-utils) --dev
```

# Known Issues / Troubleshooting
1. This utility is currently under heavy development, most of the feature may not be available.
