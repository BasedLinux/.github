# BasedOS
## Compiling an ISO
### https://nixos.org/manual/nixos/stable/#sec-building-image-instructions
```sh
git clone -b nixos-25.05-small https://github.com/BasedLinux/bsdpkgs.git
cd bsdpkgs/nixos
nix-build -j $(nproc) -A config.system.build.isoImage -I nixos-config=modules/installer/cd-dvd/installation-cd-minimal.nix default.nix
```
## Troubleshooting
- [ ] Server failures and general internet instability happen while you are bootstrapping
- [ ] Some dependencies are better off not built in parallel
- [x] Report bugs to [https://github.com/BasedLinux/bsdpkgs](basedlinux.org)
