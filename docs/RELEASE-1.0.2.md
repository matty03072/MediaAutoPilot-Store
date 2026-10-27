# Media Auto Pilot 1.0.2

Fixes administrator account setup incorrectly reporting “Installation member allowance exceeded” and blocking Discover & request on installations with available member places.

Queued administrator service setup now participates in the installation allowance before external accounts are created. The ten-member allowance, licence revocation, email verification and disabled-account restrictions remain enforced. Service setup retries retain duplicate-account safeguards.

## Upgrade from MAP 1.0.1

Back up the MAP configuration, database and encryption key together, then run the new installer over the existing MAP installation. Do not uninstall or delete its data, and do not install MAP over MPS.

- Windows: run `MAP-1.0.2-windows-x64-setup.exe` as administrator.
- Ubuntu 24.04 x64: extract `MAP-1.0.2-linux-x64.tar.gz` and run `sudo bash install.sh` from its directory.

Pending setup can retry automatically while its encrypted setup credential is valid. If the page asks you to sign in again, sign out and complete a normal sign-in including MFA. Existing external identity conflicts still require review; this release does not overwrite them.

Use `SHA256SUMS.txt` to verify downloads. Application runtime remains compiled; no first-party source is included in this public release.

## Verification

Windows and Linux each passed 125 source tests and 139 compiled-package tests, plus clean installation, managed upgrade/repair fixtures, service restart, worker heartbeat and data-retention checks. AMD64 and ARM64 containers passed anonymous pulls, layer audits and runtime checks. On-device Umbrel installation remains under investigation.
