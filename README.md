# Codewall distributions

Public downloads for Codewall's protocol and enforcement capsules and their
installer. Implementation source is maintained separately; this repository does
not contain the private source tree.

## Availability

The public distribution pipeline is being connected. **No installable release has
been published here yet.** Do not interpret this repository's existence as a
successful installation or enrollment test.

Published releases will contain:

- `install.sh`, the public bootstrap;
- a native `codewall-install` for each supported macOS/Linux target;
- `codewall-protocol.capsule` and `codewall-enforcer.capsule`;
- per-target `manifest.json` and `SHA256SUMS`.

Target-specific files are prefixed with their Rust target triple in release assets.
The bootstrap resolves one release tag before downloading, checks hashes and the
target/control-plane manifest, then invokes the installer. It does not need access
to the private source repository or a GitHub login.

## Runtime and enrollment

Codewall runs on AOS or a compatible standalone Astrid runtime. Default bootstrap
setup reconciles current stable AOS through the public AOS installer. Explicit
runtime reuse is an operator choice, not a claim that the runtime is up to date.

An enrollment token is obtained from your Codewall administrator. Enter it in the
hidden installer prompt; do not put it in a command line, issue, or release asset.
The selected runtime must start successfully before principal discovery and
enrollment. An existing but broken runtime is not a successful prerequisite check.

Initial artifacts target the staging control plane. Public download availability
does not change their enrollment authority or make them production-plane builds.

## Reporting problems

Use this repository's issues for installer and distribution problems. Include the
release tag, operating system, and redacted error output. Never include enrollment
tokens, credentials, or private tenant data.

## Rights

Public availability of binary artifacts does not grant an open-source license to
the private implementation. No additional licensing grant is made by this README.
