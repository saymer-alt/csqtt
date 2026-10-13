# CSQTT ARM64 musl — build-only spike

Upstream: https://github.com/amurcanov/csqtt
Unchanged upstream base: `71712b07dbabe16fa43f5a248dc69e1ab9f3a270`.
Original client `csqtt-client 2.1.9`; Linux target `aarch64-unknown-linux-musl`.

Build command from the technical reference (no port or packaging copied):
https://github.com/danusha2345/csqtt-android/blob/5c3cf032dade852a92bf1f2cf2bc6cd7008c428c/scripts/build_openwrt.sh

```sh
cargo +1.97.1 zigbuild --manifest-path rust-client/Cargo.toml --release --locked --target aarch64-unknown-linux-musl
```

Manual workflow: `keenetic-arm64-build.yml` on `feature/keenetic-arm64-build`.
Tools: Rust 1.97.1, Zig 0.15.2, cargo-zigbuild 0.23.4. Cargo.lock is unchanged.
Evidence includes source/tool versions, ELF headers/program headers/dynamic
dependencies, file size, SHA256, and the original LICENSE/Required Notices.
The workflow requires ELF64 little-endian AArch64, no interpreter and no NEEDED
libraries. Failure stops the job rather than publishing an unverified candidate.

Required Notice: Copyright 2026 amurcanov.
Required Notice: Commercial use of CSQTT requires a separate written license from the licensor.
Required Notice: Redistributions and derivative works must retain attribution to the original CSQTT project and these notices.

The original PolyForm Noncommercial 1.0.0 LICENSE remains unchanged. This is
only a testing Actions artifact, not a production release or public-user package.
The GitHub fork is public; artifact access follows GitHub Actions permissions,
not a claim that this repository is private. No credentials or user profiles.

No router, QEMU or network execution is part of this minimal workflow. An ELF
cross-build does not establish hardware/runtime or traffic compatibility.
No SOCKS5, TUN, MIPSel, Android, KAS, VPS or routing integration is added.
CSQTT/public qWDTT compatibility is not claimed. Further work requires a separate
owner task. Maximum two CI attempts for this spike; stop on persistent errors.
