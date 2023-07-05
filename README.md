# rtl8852bu

### Manual Installation Instructions

Note: The installation script, install-driver.sh, automates the
installation process, however, if you want to or need to do a basic
command line installation, use the following:

```
make clean
```

```
make -j$(nproc)
```

If secure boot is off:

```
sudo make install
```

```
sudo reboot
```

If secure boot is on:

Note: Please read to the end of this section before coming back here to
enter commands.

```
sudo make sign-install
```

Note: You will be promted for a password, please remember the password
as it will be used in some of the following steps.

```
sudo reboot
```

The MOK managerment screen will appear during boot:

`Shim UEFI Key Management`

`Press any key...`

Select "Enroll key"

Select "Continue"

Select "Yes"

When promted, enter the password you entered earlier.

Warning: If you enter the wrong password, your computer will not be
bootable. In this case, use the BOOT menu from your BIOS to boot then as
follows:

```
sudo mokutil --reset
```

Restart your computer. Use the BOOT menu from BIOS to boot. In the MOK
managerment screen, select `reset MOK list`, then reboot and retry from
the above step `sudo make sign-install`.

Note: If you use the Manual Installation Instructions, you will need to
repeat the installation process each time a new kernel is installed in
your distro.

-----

### Manual Removal Instructions

To remove the driver if installed by the Manual Installation
Instructions:

```
sudo make uninstall
```

```
sudo reboot
```

-----

### Driver Options (`edit-options.sh`)

Note: In Linux, driver options are called module parameters.

A file called `8852bu.conf` will be installed in `/etc/modprobe.d` by
default if you use the `install-driver.sh` script. If you are doing a
Manual Installation, you can use the 'edit-options.sh` script to 
install and/or edit the file.

Note: The installation script will prompt you to edit the options.

`8852bu.conf` will be read and applied to the driver on each system boot.

To edit the driver options file, run the `edit-options.sh` script

```
sudo ./edit-options.sh
```

Note: Documentation for Driver Options is included in the file
 `8852bu.conf`.

-----
