# TARS-v00-01 releases

This public repository contains reviewed TARS-v00-01 release artifacts and the generated xWalk developer wiki.
It replaces the former `demo-repository`; product source continues to be reviewed and submitted through Gerrit.

The published documentation is available at <https://tars-v00-01.github.io/releases/>.

## Contents

- `package/tars-v00-01.deb` is the ARM64 Debian package for Raspberry Pi 5.
- `doc/index.html` is the entry point for the generated static developer wiki.

Both artifacts were built from submitted `TARS-v00-01/xWalkPiCarAI` integration commit
`6d67a7fea14f5e8ea962086c305cdd03fcb6d124`. The package uses the repository-supported USB camera profile so it
can be built without requiring a connected camera or Robot HAT. The wiki was generated with the repository's
strict `wiki.sh verify` profile.

## Package details

| Field | Value |
| --- | --- |
| File | `package/tars-v00-01.deb` |
| Debian package | `xwalk-picarx` |
| Version | `1.0.0` |
| Architecture | `arm64` |
| SHA-256 | `d4c876521602118dfd71d5521ac9372c4e885f6069594150a6d8c5a69cafb8a5` |

Install on a supported ARM64 Raspberry Pi system:

```bash
sudo apt install ./package/tars-v00-01.deb
```

Inspect the package without installing it:

```bash
dpkg-deb --info package/tars-v00-01.deb
```

## Documentation

Read the generated wiki online at <https://tars-v00-01.github.io/releases/>. To serve the same content locally from
the repository root:

```bash
python3 -m http.server 8000 --directory doc
```

Then open `http://127.0.0.1:8000/`. Regenerate documentation in the integration workspace with:

```bash
xWalk-rpi5-tool/doc-tool/wiki.sh verify
```

## Publication policy

Changes to product source belong in the owning Gerrit projects. This repository stores only release packages and
generated documentation. Product defects and release requests are tracked in Jira; GitHub Issues are disabled.
The published site uses a dedicated `gh-pages` branch and does not require a billable GitHub Actions workflow.
