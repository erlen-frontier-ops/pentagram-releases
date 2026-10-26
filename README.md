# Pentagram desktop releases

This public repository hosts signed desktop builds of Pentagram, the update manifest the application reads, and corresponding-source release assets. It does not host the Pentagram application source tree or its development history.

## Release assets

Each `v<version>` release contains:

- `Pentagram_<version>_amd64.AppImage` — portable Linux x86_64 build;
- `Pentagram_<version>_amd64.deb` — Debian/Ubuntu package;
- `<asset>.sha256` — SHA-256 checksum for each build;
- `<asset>.sig` — minisign signature for each build; the AppImage signature is also the updater signature.

Verify a download before installing:

```sh
sha256sum -c Pentagram_<version>_amd64.AppImage.sha256
```

The application verifies update signatures itself before installing an update.

## License and third-party notices

Pentagram is distributed under the MIT license. The license text and the third-party notices for the bundled libraries are installed with the application in `/usr/share/doc/pentagram/`.

## Corresponding sources

The desktop builds bundle GPL/LGPL components. Their corresponding sources are published once per SDK as a `sources-<sdkid>` release, linked from each version's publication. Source archives, origins and checksums are listed in that release's `SOURCES.md` asset.

## Update channel

The application updater reads the `latest.json` asset of the `updater` release:

<https://github.com/erlen-frontier-ops/pentagram-releases/releases/download/updater/latest.json>

Every update is installed only after the application verifies its minisign signature.

## Public signing key

The value below is the minisign public key file in base64 form, the form the Tauri updater configuration uses.

```text
dW50cnVzdGVkIGNvbW1lbnQ6IG1pbmlzaWduIHB1YmxpYyBrZXk6IDI3RkM3REUzNTA4RjAzNzUKUldSMUE0OVE0MzM4SjM4U0pDSDlPRm5lVml6NytHUm9uMEZGdEE1S1ZkYXVvcGhkeUxXSWtFeDQK
```
