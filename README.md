# Jcmp-pkg

Packages for [Jaric](https://github.com/J2k-studio/Jcmp): programs that J2K does not (yet) replace — git, clang, python, ssh, java, rust ...
`jc install NAME` reads `index.json`, downloads the archive, checks its sha256 and unpacks it into `~/.jaric/pkg/NAME/VERSION`, then links its programs into `bin`.

* Built for Jaric's own prefix (not Termux's: Termux binaries have `/data/data/com.termux/...` inside them).
* Architectures: `aarch64` first, `arm` later.
* Big packages (clang, java, rust) are downloaded only when asked for; `jc` shows the size first.

## Files
* `index.json` — the list of packages (format in `SPEC.md`). Written by the build, never by hand.
* `recipes/NAME.sh` — how a package is built (a build script of termux-packages with the Jaric prefix).
* `.github/workflows/build.yml` — builds the packages on GitHub Actions and attaches them to a release.

See [PACKAGES.md](PACKAGES.md) for the list of packages that are planned (git, clang, python, dropbear (ssh), java (openjdk), rust, node, sqlite, ffmpeg and the usual small tools) and in what order.

## Status
Started 2026-10-29. Nothing is published yet: the first goal is `git`, then `clang`, `python`, `dropbear` (ssh).
