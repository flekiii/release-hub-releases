# Publishing Release Hub for Linux

No executable release is published until it has passed Linux CI, local smoke tests, and at least one independent distro test.

## Trusted update sequence

1. Build the Linux application from reviewed private source.
2. Prepare and manually verify a portable Linux distribution.
3. Upload the **actual build** to a tagged GitHub Release (`vX.Y.Z`) in this public repository.
4. Generate `updates/stable.json` or `updates/beta.json` from the exact asset bytes, including version, download URL, size and SHA-256.
5. Sign the unchanged JSON bytes using the offline Ed25519 private key owned by Fleki. Publish the detached `.sig` beside the JSON.
6. The Release Hub Linux client verifies the detached signature against its **embedded public key** and checks the downloaded file's size and digest before presenting it for manual installation.

**Never store the private key in GitHub.** A hash alone does not authenticate an update. Do not publish unsigned update metadata. The Update Engine cannot enforce licensing on old offline binaries; later cloud features must be checked server-side.

## Distribution roadmap

| Artifact | Status |
|---|---|
| portable `.tar.gz` x86_64 | Build scripts prepared; runtime tests pending |
| AppImage x86_64 | Planned |
| Debian `.deb` x86_64 | Planned |
| RPM x86_64 | Planned |
| Arch `.pkg.tar.zst` x86_64 | Planned |
| Flatpak | Planned |
| Snap | Planned |
| ARM64 | Pending dependency compatibility and native tests |

The project's website will link only to formats that have been built, checked, and released.
