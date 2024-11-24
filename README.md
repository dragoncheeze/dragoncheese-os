# dragoncheese-os &nbsp; [![bluebuild build badge](https://github.com/dragoncheeze/dragoncheese-os/actions/workflows/build.yml/badge.svg)](https://github.com/dragoncheeze/dragoncheese-os/actions/workflows/build.yml)

This is a simple Sway Atomic image using [BlueBuild docs](https://blue-build.org/how-to/setup/).
Just a few tweaks made to the default Ublue-os Fedora Sericea image.
 - using Brave as default browser
 - added Lutris as flatpak
 - distrobox, neovim, fish, and other default apps installed.
 - custom minimal configuration for sway


## Installation

To rebase an existing atomic Fedora installation to the latest build:

> **NOTE**
>
> Use dragoncheese-os for AMD gpu
>
> Use dragoncheese-nvidia for NVIDIA gpu


- **First** rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/dragoncheeze/dragoncheese-os:latest

  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- **Then** rebase to the signed image (this is not optional):
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/dragoncheeze/dragoncheese-os:latest
=======
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```
