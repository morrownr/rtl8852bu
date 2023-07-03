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

You will be promted for a password, please remember the password as it
will be used in some of the following steps.

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

If you enter the wrong password, your computer will not be bootable. In
this case, use the BOOT menu from your BIOS to boot then as follows:

```
sudo mokutil --reset
```

Restart your computer and use the BOOT menu from BIOS to boot. In the MOK
managerment screen, select `reset MOK list`. Then Reboot and retry from
the step `sudo make sign-install`.

To remove the driver if installed by the Manual Installation
Instructions:

```
sudo make uninstall
```

```
sudo reboot
```
