---
title: Linux
pcx_content_type: how-to
weight: 0
meta:
  title: Linux desktop client
---

# Linux desktop client

You have two ways of installing WARP on Linux, depending on the distro you are using:

- Find the latest WARP client in the [package repository](https://pkg.cloudflareclient.com/).
- Install the `cloudflare-warp` package that suits your distro:
  - **apt-based OS** (like Ubuntu): `sudo apt install cloudflare-warp`.
  - **yum-based OS** (like CentOS or RHEL): `sudo yum install cloudflare-warp`.

{{<Aside type="note">}}

If you get an error message when trying to install via the terminal, download the package that suits your distro from the [package repository](https://pkg.cloudflareclient.com/).

{{</Aside>}}

## Using WARP

The command line interface is the primary way to use WARP.

### Initial Connection

To connect for the very first time:

1. Register the client `warp-cli registration new`.
2. Connect `warp-cli connect`.
3. Run `curl https://www.cloudflare.com/cdn-cgi/trace/` and verify that `warp=on`.

### Switching modes

You can use `warp-cli set-mode --help` to get a list of the modes to switch between. For example:

- **DNS only mode via DoH:** `warp-cli set-mode doh`.
- **WARP with DoH:** `warp-cli set-mode warp+doh`.

### Using 1.1.1.1 for Families

The Linux client supports all 1.1.1.1 for Families modes, in either WARP on DNS-only mode:

- **Families mode off:** `warp-cli set-families-mode off`
- **Malware protection:** `warp-cli set-families-mode malware`
- **Malware and adult content:** `warp-cli set-families-mode full`

### Additional commands

A complete list of all supported commands can be found by running:

```sh
$ warp-cli --help
```

## Feedback

You can find logs required to debug WARP issues by running `sudo warp-diag`. This will place a `warp-debugging-info.zip` file in the path from which you ran the command.

To report bugs or provide feedback to the team use the command `sudo warp-diag feedback`. This will submit a support ticket.
