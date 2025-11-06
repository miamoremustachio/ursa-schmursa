![](screenshot.png)

A fork of [csteinforth](https://github.com/csteinforth)'s fork of [Ken Goettler](https://github.com/kgoettler)'s Ursa Major rEFInd theme:

*https://github.com/kgoettler/ursamajor-rEFInd*

Icons are included for a variety of Linux distributions, as well as macOS and 
Windows.

## Installation

1. Locate your rEFInd directory:

```bash
cd /boot/efi/EFI/refind # for most linux based systems
```

2. Clone this repo to the `themes` directory inside the rEFInd directory:

```bash
sudo mkdir themes
cd themes
git clone https://github.com/miamoremustachio/ursa-schmursa.git
```

3. Add the following line at the bottom of the `refind.conf` file:

```bash
include themes/ursa-schmursa/theme.conf
```

## Configuration

By default, rEFInd will create entries for any `.efi` files found in the EFI
directory on your boot volume. 

You can exclude certain directories containing `.efi` files by passing them
to the `dont_scan_dirs` token of the `refind.conf` file:

```bash
# Exclude any .efi files found in /EFI/BOOT and /EFI/old
dont_scan_dirs /EFI/BOOT,/EFI/old
```

You can also exclude specific `.efi` files themselves by passing them to the 
`dont_scan_files` token of the `refind.conf` file:

```bash
# Exclude /EFI/ubuntu/mmx64.efi and any .efi file named shimx64.efi
dont_scan_files /EFI/ubuntu/mmx64.efi,shimx64.efi
```

You can also change the icon used for a particular `.efi` file by placing a
`.png` file of the same name in the directory with it:

```bash
$ ls /boot/EFI/BOOT

BOOTX64.EFI BOOTX64.PNG
```

## Additional Information

Additional info about configuring rEFInd may be found [here](http://www.rodsbooks.com/refind/configfile.html).
