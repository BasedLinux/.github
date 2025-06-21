# BasedOS
## Compiling an ISO
```sh
git clone -b nixos-25.05-small https://github.com/BasedLinux/bsdpkgs.git
cd bsdpkgs/nixos
# See https://nixos.org/manual/nixos/stable/#sec-building-image-instructions
nix-build -A config.system.build.isoImage -I nixos-config=modules/installer/cd-dvd/installation-cd-minimal.nix default.nix
```
