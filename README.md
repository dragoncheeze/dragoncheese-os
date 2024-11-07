# dragoncheese-os &nbsp; [![bluebuild build badge](https://github.com/dragoncheeze/dragoncheese-os/actions/workflows/build.yml/badge.svg)](https://github.com/dragoncheeze/dragoncheese-os/actions/workflows/build.yml)

This is a simple Sway Atomic image using [BlueBuild docs](https://blue-build.org/how-to/setup/).
Just a few tweaks made to the default Ublue-os Fedora Sericea image.
 - using Brave as default browser
 - added Lutris as flatpak
 - distrobox, neovim, fish, and other default apps installed.
 - custom minimal configuration for sway


## Installation

> **Warning**
> [This is an experimental feature](https://www.fedoraproject.org/wiki/Changes/OstreeNativeContainerStable), try at your own discretion.
>

To rebase an existing atomic Fedora installation to the latest build:

> **NOTE**
> Use dragoncheese-os for AMD gpu
>
> dragoncheese-nvidia for NVIDIA gpu


- First rebase to the unsigned image, to get the proper signing keys and policies installed:
  ```
  rpm-ostree rebase ostree-unverified-registry:ghcr.io/dragoncheeze/dragoncheese-os:latest
  ```
- Reboot to complete the rebase:
  ```
  systemctl reboot
  ```
- Then rebase to the signed image, like so:
  ```
  rpm-ostree rebase ostree-image-signed:docker://ghcr.io/dragoncheeze/dragoncheese-os:latest
  ```
- Reboot again to complete the installation
  ```
  systemctl reboot
  ```

The `latest` tag will automatically point to the latest build. That build will still always use the Fedora version specified in `recipe.yml`, so you won't get accidentally updated to the next major version.

## ISO

If build on Fedora Atomic, you can generate an offline ISO with the instructions available [here](https://blue-build.org/learn/universal-blue/#fresh-install-from-an-iso). These ISOs cannot unfortunately be distributed on GitHub for free due to large sizes, so for public projects something else has to be used for hosting.

## Verification

These images are signed with [Sigstore](https://www.sigstore.dev/)'s [cosign](https://github.com/sigstore/cosign). You can verify the signature by downloading the `cosign.pub` file from this repo and running the following command:

```bash
cosign verify --key cosign.pub ghcr.io/dragoncheeze/dragoncheese-os
```
