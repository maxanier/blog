---
slug: pacman-unknown-trust
title: Manjaro - Pacman corrupted package - unknown trust
authors: max
tag: linux
---

When updating packages (after a long time), sometimes all packages are considered corrupted because the PGP signature is not accepted:
`invalid or corrupted package (PGP signature))` `Unknown trust.`

To fix on Manjaro:
<!-- truncate -->
```
sudo pacman -Syy
sudo pacman-key --refresh-keys
sudo pacman-key --populate archlinux manjaro
sudo pacman -S manjaro-keyring
```
Alternatively
```
sudo rm -r /etc/pacman.d/gnupg
sudo pacman-key --init
sudo pacman-key --populate archlinux manjaro
sudo pacman -S manjaro-keyring
```