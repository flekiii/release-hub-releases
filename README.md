# Release Hub — Official Linux Releases

This public repository hosts **downloadable, verified Linux releases** and later signed update manifests for [Release Hub](https://github.com/flekiii).

**Status: No stable release is published yet.** Do not download or install files from unofficial sources.

## Planned formats
Portable `.tar.gz`, AppImage, `.deb`, `.rpm`, Arch Linux `.pkg.tar.zst`; Flatpak, Snap and ARM64 only when tested.

## Security
Artifacts will include SHA-256 checksums. Update manifests will require a trusted digital signature; a checksum on its own is not authentication. The app will not silently execute downloaded installers.

## Channels
- `stable`: tested public releases
- `beta`: opt-in previews

Release Hub is built by Fleki. Website: https://flekiii.github.io/
