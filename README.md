# limine_conf

My personal [Limine](https://github.com/limine-bootloader/limine) bootloader configuration for Arch Linux + Windows 11 dual boot.

## Theme

[Catppuccin Mocha](https://github.com/catppuccin/catppuccin) color palette with custom wallpaper.

## Setup

- **Bootloader:** Limine
- **OS 1:** Arch Linux (Niri, Wayland)
- **OS 2:** Windows 11
- **Resolution:** 2560x1440
- **Filesystem:** Btrfs

## Structure

```
/
├── limine.cfg        # Main bootloader config
└── limine/
    └── blue-dragon-girl.jpg  # Boot wallpaper
```

## Usage

After reinstalling or changing the Linux partition, update the `PARTUUID` in `limine.cfg`:

```bash
# Find new PARTUUID
lsblk -o NAME,PARTUUID

# Then update this line in limine.cfg:
# cmdline: root=PARTUUID=<your-new-partuuid> rw rootfstype=btrfs
```

Then write the config back to the EFI partition.
