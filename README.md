# Introduction
This guide documents the specific steps needed after the initial installation of Debian on my Lenovo ideapad 320.

## Fix issue with backlight
```
# sed -i '/GRUB_CMDLINE_LINUX_DEFAULT=/c\GRUB_CMDLINE_LINUX_DEFAULT=\"quiet acpi_backlight=none amdgpu.dc=0\"' /etc/default/grub
# grub-mkconfig -o /boot/grub/grub.cfg
```

## Install nftables
Download the package and copy the file `conf/nftables.conf` to `/etc/`.

```
# apt install nftables
# mv conf/nftables.conf /etc/
# systemctl enable nftables.service
```

## Clear error on systemd network initialization
```
# rm /etc/network/interfaces.d/*

```

# Add necessary firmware files for atheros card

Download latest atheros firmware from here: http://ftp.us.debian.org/debian/pool/non-free/f/firmware-nonfree/.

After download, run the following: 
```
dpkg -i firmware-atheros_xxx_all.deb
```

