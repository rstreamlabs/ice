<!-- SPDX-FileCopyrightText: 2026 The Pion community <https://pion.ly> -->
<!-- SPDX-License-Identifier: MIT -->

# rstream fork of Pion ICE

This repository maintains the compatibility fork retaining serialized ICE URL snapshots during candidate gathering. It derives from [Pion ICE](https://github.com/pion/ice) and retains the upstream Go module identity and MIT license.

This is a compatibility source for consumers still pinned to the fork. Current first-party builds use the official ICE module with their verified build-time patch; follow the owning consumer’s module file and build instructions.

Use the [fork guide](RSTREAM_FORK.md) to understand the retained changes and compatibility constraints before selecting a revision. Applications pin reviewed immutable replacements in their own module graph; a pseudo-version’s ancestor tag alone does not describe the reviewed source.

| Task                                | Start here                                                                                                                               |
| ----------------------------------- | ---------------------------------------------------------------------------------------------------------------------------------------- |
| Integrate rstream in an application | [Go reference SDK](https://github.com/rstreamlabs/rstream-go) or [application examples](https://github.com/rstreamlabs/rstream-examples) |
| Understand this fork                | [Retained behavior and maintenance](RSTREAM_FORK.md)                                                                                     |
| Learn the upstream API              | [Pion ice](https://github.com/pion/ice)                                                                                                  |
| Review source examples              | [Examples](examples)                                                                                                                     |
| Contribute to upstream Pion         | [Contribution guide](https://github.com/pion/webrtc/wiki/Contributing)                                                                   |

For rstream-specific changes, use this repository’s issues and preserve the fork regressions. Report vulnerabilities privately through the [rstream security policy](https://github.com/rstreamlabs/.github/blob/main/SECURITY.md). Upstream attribution and license terms are in [LICENSE](LICENSE).
