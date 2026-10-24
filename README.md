# SPS OTA test releases

Current release: **1.0.1+0** for the BL54L15 SPS carrier.

The device downloads the standard SDK release pair from `dfu_application/`:

- `manifest.json`
- `smart_power_socket.signed.bin`

Start the field test with the matching 1.0.0+0 MCUboot/application SWD image, wait for `Health=OK/60s` and `Backup=Ready`, then send `ota=1.0.1`. After installation, send `getotainfo` and check `FW=1.0.1+0`.

These development images use the MCUboot SDK example Ed25519 signing key. The installed bootloader and release signer must use the same key. This repository contains signed artifacts only; do not upload private signing keys.

The named signed binary is the unchanged payload from `dfu_application.zip`. Publish its matching manifest and binary together when replacing a release. Do not edit their version/size fields manually.
