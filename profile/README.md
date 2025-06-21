# BasedOS
## Compiling an ISO
```sh
git clone -b nixos-25.05-small https://github.com/BasedLinux/bsdpkgs.git
cd bsdpkgs/nixos
# See https://nixos.org/manual/nixos/stable/#sec-building-image-instructions
nix-build -A config.system.build.isoImage -I nixos-config=modules/installer/cd-dvd/installation-cd-minimal.nix default.nix
```
## Troubleshooting
Server failures and general internet instability can happen while you are bootstrapping Nix from source. Some servers don't always respond! Additionally, some dependencies are better off not built in parallel.

`nix-build` can be restricted to a number of threads with the -j flag. So, you might find that running this in a loop is helpful:

```sh
while true; do nix-build -j 1 -A config.system.build.isoImage -I nixos-config=modules/installer/cd-dvd/installation-cd-minimal.nix default.nix; sleep 60; nix-build -A config.system.build.isoImage -I nixos-config=modules/installer/cd-dvd/installation-cd-minimal.nix default.nix; sleep 60; done
```
