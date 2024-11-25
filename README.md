# dragoncheese-os &nbsp; [![bluebuild build badge](https://github.com/dragoncheeze/dragoncheese-os/actions/workflows/build.yml/badge.svg)](https://github.com/dragoncheeze/dragoncheese-os/actions/workflows/build.yml)

This is simple Fedora Atomic images using [BlueBuild docs](https://blue-build.org/how-to/setup/).
Just a few tweaks made to the default Universal Blue images.
 - using Brave as default browser
 - added Lutris as flatpak
 - distrobox, neovim, fish, and other default apps installed.
 - custom minimal configuration for the sway image


## Installation

Install any official Fedora Atomic image (recommend using sway) then rebase to one of these images:

> Available Images:
>
> sway
>
> sway-nvidia
>
> gnome
>
> gnome-nvidia
>


- **First** rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/dragoncheeze/sway:latest

  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- **Then** rebase to the signed image (this is not optional):
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/dragoncheeze/sway:latest
  
- Reboot again to complete the installation
  
  ```
  systemctl reboot
  ```
