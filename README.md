# auto-epp

**auto-epp** is a python script that manages the energy performance preferences (EPP) of your AMD CPU using the AMD-Pstate driver. It adjusts the EPP settings based on whether your system is running on AC power or battery power, helping optimize power consumption and performance.

## Index

- [Requirements](#requirements)
- [Enable amd-pstate-epp](#to-enable-amd-pstate-epp)
- [Installation](#installation)
- [Usage](#usage)

## Requirements

- AMD CPU with the AMD-Pstate-EPP driver enabled.
- Python 3.x
- psutil library(install using your package manager)

## To enable amd-pstate-epp

This can be done by editing the `GRUB_CMDLINE_LINUX_DEFAULT` params in `/etc/default/grub`. Follow these steps:

1. Open the grub file using the following command:
```bash
sudo nano /etc/default/grub
```
2. Within the file, modify the `GRUB_CMDLINE_LINUX_DEFAULT` line to include the setting for AMD P-State EPP:
```bash
GRUB_CMDLINE_LINUX_DEFAULT="quiet splash amd_pstate=active"
```

## Installation

```bash
git clone https://github.com/jothi-prasath/auto-epp
cd auto-epp
chmod +x ./install.sh
sudo ./install.sh
```

## Usage

Monitor the service status
```bash
systemctl status auto-epp
```

To restart the service
```bash
sudo systemctl restart auto-epp
```

Edit the config file
```bash
sudo nano /etc/auto-epp.conf
```