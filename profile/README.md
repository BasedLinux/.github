# BasedOS
## Compiling an ISO
### https://nixos.org/manual/nixos/stable/#sec-building-image-instructions
```sh
# as root
git clone -b nixos-25.05-small https://github.com/BasedLinux/bsdpkgs.git
cd bsdpkgs/nixos
export NIX_STORE_DIR=/bsd/store
nix-build -j $(nproc) -A config.system.build.isoImage -I nixos-config=modules/installer/cd-dvd/installation-cd-minimal.nix default.nix
```
## Troubleshooting
- [ ] Server failures and general internet instability happen while you are bootstrapping
- [ ] Some dependencies are better off not built in parallel. Try running only 1 job if all else fails
- [ ] git.savannah.gnu.org is especially slow and contains a lot of required patches for grub
- [x] Report bugs to [basedlinux.org](https://github.com/BasedLinux/bsdpkgs/issues/new)
