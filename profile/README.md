<!-- SPDX-License-Identifier: GPL-3.0-only -->
# OnlyCrayZ-Labs

OnlyCrayZ-Labs develops experimental open-source compatibility work for running
Microsoft Flight Simulator 2024 on Linux. Our immediate focus is stability,
reproducible installation and a practical Linux launcher.

## MSFS 2024 on Linux

Our first successful, user-reported in-game test used the Microsoft Store / Xbox
PC edition with a standard aircraft included with MSFS 2024, on CachyOS Linux
with an NVIDIA RTX 5090. The recorded setup reached the menu and world map,
then a flight with cockpit and landscape rendering, working instruments and
user input, using Xodus and a modified Wine/Proton runtime.

This milestone belongs to a preserved private checkpoint. The public source
preview still needs clean-installation validation; it is not a verified binary
runtime release or a supported installer. Long-flight stability, performance,
restart persistence and compatibility across hardware remain unverified.
Xbox cloud-save synchronization is not implemented. Fenix A320, Navigraph,
BeyondATC and other third-party add-ons have not been validated; no working
third-party add-on compatibility is claimed.

## Repositories

| Project | Purpose |
| --- | --- |
| [MSFS2024-Linux](https://github.com/OnlyCrayZ-Labs/MSFS2024-Linux) | Main project overview, limitations, documentation and issue intake |
| [xodus](https://github.com/OnlyCrayZ-Labs/xodus) | Authentication and licensing service and launch tooling |
| [xodus-proton](https://github.com/OnlyCrayZ-Labs/xodus-proton) | SDK-free source integration manifest with pinned Wine sources |
| [wine](https://github.com/OnlyCrayZ-Labs/wine) | Experimental Wine integration |
| [xgameruntime](https://github.com/OnlyCrayZ-Labs/xgameruntime) | Open-source runtime compatibility component |

## Technical overview

Xodus provides the authentication/licensing service and launch tooling. The
modified Wine/Proton environment runs the Windows game, while the open-source
xgameruntime component connects runtime requests to the Xodus service and a
local save provider. Title-specific endpoint selection supports the Microsoft /
Xbox authentication flow used in the recorded MSFS 2024 test.

The public xodus-proton repository is an integration manifest, not a complete
Proton distribution. Building a full runtime requires separately obtained
upstream sources and review of their SDK terms. A legitimate game license and
your own game installation are required. We do not distribute game files,
credentials, Wine prefixes or private milestone binaries.

## Roadmap

1. Stability and reproducible installation.
2. Basic Linux launcher.
3. Basic add-on compatibility.
4. Fenix A320, Navigraph, BeyondATC and other third-party add-ons.
5. Full launcher with automatic updates and add-on management.

These are development goals, not statements of current compatibility.

## Contributing

Start with the [main project](https://github.com/OnlyCrayZ-Labs/MSFS2024-Linux),
its [contribution guide](https://github.com/OnlyCrayZ-Labs/MSFS2024-Linux/blob/main/CONTRIBUTING.md)
and [security policy](https://github.com/OnlyCrayZ-Labs/MSFS2024-Linux/blob/main/SECURITY.md).
Useful contributions include reproducible bug reports, installation documentation,
stability testing and focused component pull requests. Include relevant version
and hardware information, and remove account data and secrets from diagnostics.
Report sensitive vulnerabilities privately through the affected repository's
Security tab. OnlyCrayZ controls official development merges and releases.

## Attribution and licensing

Our work builds on xodus-gaming, Wine, Valve/Proton and their contributors.
Existing upstream copyright notices and component licenses remain applicable;
this profile does not relicense any component. This original profile text is
GPL-3.0-only. Microsoft Flight Simulator, Microsoft and Xbox are trademarks of
their respective owners. This independent community project is not affiliated
with or endorsed by Microsoft, Asobo, Valve or upstream Xodus.
