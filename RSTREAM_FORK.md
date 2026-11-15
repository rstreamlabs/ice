<!-- SPDX-FileCopyrightText: 2026 The Pion community <https://pion.ly> -->
<!-- SPDX-License-Identifier: MIT -->

# rstream ICE fork

This fork retains a concurrency correction for updates to ICE server URLs during candidate gathering. Each gathering cycle captures a URL snapshot on the agent task loop; network gathering runs against that snapshot. This serializes option updates without holding the loop during network I/O.

The source correction and regression are in `gather.go` and `agent_test.go`. Keep the initial and continual-gathering paths covered when updating upstream source. The module uses the upstream import path `github.com/pion/ice/v4`; consumers select a reviewed fork revision through an explicit replacement.

## Consumer boundary

The current Go SDK and video examples use the official ICE dependency with their verified build-time patch, rather than selecting this compatibility fork. Follow the owning consumer’s module file and build guide; these are separate build inputs and are not interchangeable replacements.

## Maintenance checks

Use the Go version declared in `go.mod`:

```sh
go test -race ./...
go vet ./...
```

Retain the supported-platform and API checks, along with the DNS-parser security floor. An upstream release can replace this fork only after the URL-update concurrency behavior and consuming application tests pass.

## Build this checkout

Use the Go version declared in `go.mod` or a compatible newer toolchain. From the
repository root, `go build ./...` compiles the library packages and included
commands without application credentials. Locked modules must be available in
the Go cache or downloaded first. Keep the upstream module path: consumers select
this fork through their reviewed module replacement and immutable revision, not
by renaming imports or installing an upstream `latest` release.

This build is a local first check. The qualification requirements above still
apply; it does not certify consuming applications or replace their pinned
dependency graph. Upstream usage and attribution remain in `README.md`.
