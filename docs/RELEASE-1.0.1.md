# Media Auto Pilot 1.0.1

First MAP release, based on the released MPS customer 1.0.4 application.

## What changed

- Media Auto Pilot branding, independent licence authority and installation/service identities.
- Removed Admin Revenue, Monthly Plans, member checkout and member payment settings. Member access is governed by verification, administrator permissions and the installation licence—not member payment status.
- Retained automatic Emby/Jellyfin/Ombi account setup, library permissions, password synchronization, account removal, media requests, Sonarr/Radarr management, MFA and CSRF protection.
- Free allowance of ten managed members; a MAP software licence unlocks more members on up to three installations. Licence account: https://www.mediaautopilot.co.uk/map/account.
- Minimal signed installation activity reporting remains enabled.

## Installation

MAP is a separate product and a fresh installation. **Do not install it over MPS or reuse an MPS database/state directory.** Windows uses MAP services and directories; Linux uses `/opt/map`, `/etc/map` and `/var/lib/map`; the Umbrel community app uses its own `mediaautopilot-map` identity and port 18100.

Download `MAP-1.0.1-windows-x64-setup.exe` or `MAP-1.0.1-linux-x64.tar.gz` with `SHA256SUMS.txt`. The Linux archive targets Ubuntu 24.04 x64. Keep configuration, encryption key and database together in backups.

## Verification

- 121 customer regression/product tests, 50 installer/setup tests, 79 issuer tests.
- Windows x64 and Ubuntu 24.04 x64 native build, payload/source audit, clean install, same-version repair, real web/worker services, restart and data-preserving uninstall passed in CI.
- Downloaded Linux archive: 131 manifest hashes and first-party source exclusion checked again. Published installer hashes are supplied separately.
- AMD64 and ARM64 container builds, every-layer source audit, compiled-runtime tests and web/worker restart checks passed before publication. Anonymous registry verification is required before the public community manifest is activated.
- MAP reporting/isolation checks passed locally and on the Windows host. Customer, website and Beta owner screens were checked at desktop/mobile widths using isolated fixtures.

First-party runtime code is compiled; the release excludes first-party Python source/bytecode and build intermediates. This is not a guarantee against reverse engineering. The public repository contains distribution documentation and metadata, not private application source.

## Limits

- No actual on-device umbrelOS installation or upgrade was performed; this is a community preview, not an official Umbrel App Store release.
- External SQL Server/PostgreSQL installation/upgrade acceptance is not established by SQLite or schema-compilation tests.
- Provider lifecycle tests use isolated fake services. MAP-specific live playback, Live TV, multiple real Jellyfin servers and complete real portal-linked lifecycle were not repeated for this fork.
- Screenshots show the running source fixture with demonstration data, not an installed compiled-package capture.
- Licence purchase/refund/activation flows were tested with mocked payment events; no real customer was charged as a release test.
