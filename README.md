# hwsight-data

Device data for [hwsight](https://github.com/sweatshopking/hwsight), the friendly Device
Manager for Linux.

hwsight keeps its knowledge about hardware in data files, so it can learn about new
devices without a new app release. The files are published here as
[releases](https://github.com/sweatshopking/hwsight-data/releases):

| File | What it is |
|---|---|
| `rules.toml` | Which devices need no driver, and what a working driver should create |
| `firmware.toml` | Which package provides missing firmware, for each distro and release |
| `descriptions.toml` | What each kind of device does, in plain English |
| `pci.ids`, `usb.ids` | Device names, from the upstream ID databases |
| `manifest.toml` | Version, size, and checksum of every file |
| `manifest.toml.sig` | Signature over the manifest |

## How updates stay safe

hwsight only installs a file when the manifest's signature matches a key built into
hwsight, the file's size and checksum match the manifest, and the file loads correctly.
If anything fails, nothing is installed and hwsight keeps using what it already has.

## Sources and licences

- `rules.toml`, `firmware.toml`, and `descriptions.toml` are part of hwsight:
  GPL-3.0-or-later.
- `pci.ids` comes from [The PCI ID Repository](https://pci-ids.ucw.cz/) and `usb.ids`
  from [The USB ID Repository](http://www.linux-usb.org/usb-ids.html). Both are
  available under GPL-2.0-or-later or BSD-3-Clause; see the headers in each file.

The data files themselves are edited in the hwsight repository (`hwsight-core/data/`)
and published here by its release script.
