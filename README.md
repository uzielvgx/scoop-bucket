# VGXNESS Scoop bucket

With Scoop already installed on Windows:

```powershell
scoop bucket add vgxness https://github.com/uzielvgx/scoop-bucket
scoop install vgxness/vgxness
vgxness version
```

The manifest selects Windows amd64 or arm64 and verifies the pinned release
SHA-256. It contains no installer scripts or hooks. Scoop owns its app directory
and shim, not your coding hosts, credentials, integrations or memories.

After configuring the desired coding hosts, preview/apply with the Scoop binary:

```powershell
& "$(scoop prefix vgxness)/vgxness.exe" setup all --preview
& "$(scoop prefix vgxness)/vgxness.exe" setup all --yes
```

Use `vgxness tui` for model selection. After `scoop update vgxness`, rerun setup
with the Scoop-owned binary to update a separate managed launcher. Uninstalling
Scoop's package does not remove managed integrations or memory.

Windows Pi workers are unsupported. Windows amd64 has native release-archive
validation; arm64 is distributed without an exact-tag native smoke gate.
[Full support limits](https://github.com/uzielvgx/vgxness/blob/main/docs/v1-readiness.md).

Maintainers copy the published `vgxness.json` release asset to
`bucket/vgxness.json` after verifying checksums. Native CI installs the exact
checked-out manifest using a pinned Scoop revision and verifies its version.
