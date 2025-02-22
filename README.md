# Pop!\_OS 21.10 Beta Testing

Thank you for participating in Pop!\_OS 21.10 beta release testing! This release integrates COSMIC with GNOME 40. There are many corner cases with those features that your testing will help reveal.

**THIS IS A BETA**. Bugs are expected and re-installs are likely.

## Installing or Upgrading

We're seeking upgrade testing as well as fresh install testing. You can upgrade to Pop!\_OS 21.10 from Pop!\_OS 21.04. It is recommended that you backup your data, download the Pop!\_OS 21.10 Beta ISO and write it to a USB drive first.

Pop!\_OS 21.10 Beta ISOs are located here:

Intel/AMD Graphics ISO:
- [ISO](https://pop-iso.sfo2.cdn.digitaloceanspaces.com/21.10/amd64/intel/3/pop-os_21.10_amd64_intel_3.iso)
- [SHA256SUMS](https://pop-iso.sfo2.cdn.digitaloceanspaces.com/21.10/amd64/intel/3/SHA256SUMS)
- [SHA256SUMS.gpg](https://pop-iso.sfo2.cdn.digitaloceanspaces.com/21.10/amd64/intel/3/SHA256SUMS.gpg)

NVIDIA Graphics ISO:
- [ISO](https://pop-iso.sfo2.cdn.digitaloceanspaces.com/21.10/amd64/nvidia/3/pop-os_21.10_amd64_nvidia_3.iso)
- [SHA256SUMS](https://pop-iso.sfo2.cdn.digitaloceanspaces.com/21.10/amd64/nvidia/3/SHA256SUMS)
- [SHA256SUMS.gpg](https://pop-iso.sfo2.cdn.digitaloceanspaces.com/21.10/amd64/nvidia/3/SHA256SUMS.gpg)

Experimental Raspberry Pi 4 (and 400) Image:
- You must have at least 8GB of storage and 4GB of RAM. It is recommended to boot from a USB 3 drive for performance reasons.
- The root partition will not automatically expand yet, and must be expanded manually.
- [Image](http://pop-iso.sfo2.digitaloceanspaces.com/21.10/arm64/raspi/4/pop-os_21.10_arm64_raspi_4.img.xz)
- [SHA256SUMS](http://pop-iso.sfo2.digitaloceanspaces.com/21.10/arm64/raspi/4/SHA256SUMS)
- [SHA256SUMS.gpg](http://pop-iso.sfo2.digitaloceanspaces.com/21.10/arm64/raspi/4/SHA256SUMS.gpg)

Before upgrading an existing Pop!\_OS installation, run these commands to collect information about your system's installed sources and packages:
```
cat /etc/apt/sources.list >> sources.txt
ls -alh /etc/apt/sources.list.d/ >> sources.txt
cat /etc/apt/sources.list.d/* >> sources.txt
apt list --installed > packages.txt
```
Save these files in case they're needed to recreate any issues encountered while upgrading.

Then, upgrade from Pop!\_OS 21.04 to Pop!\_OS 21.10 with the command:
```
sudo pop-upgrade release upgrade -f
```

If you encounter issues running the `pop-upgrade` command, you can view the daemon logs with the command:

```
sudo journalctl -u pop-upgrade
```

Alternatively, in a second terminal window you can stop the system daemon and then run the daemon in the foreground with the commands:

```
sudo systemctl stop pop-upgrade
sudo pop-upgrade daemon
```
and then run the upgrade command again. When you are finished, you can restart the system daemon with the command:

```
sudo systemctl start pop-upgrade
```

## Reporting Issues

Report issues you encounter on this repository. Issues will be triaged and added to the [Pop!\_OS 21.10 project](https://github.com/orgs/pop-os/projects/16). If you have any usability feedback, label issues with `ux` tag or contact our UX architect at ux@system76.com.

## Release Notes

Release notes will be available later.
