# Tony's neutronics toolbox

<!-- [![Build Status][test-img]][test-url] -->
[![Documentation][doc-img]][doc-url]

<!-- [test-img]: https://github.com/repositony/ntools/actions/workflows/tests.yml/badge.svg
[test-url]: https://github.com/repositony/ntools/actions/workflows/tests.yml -->

[doc-img]: https://img.shields.io/badge/docs-latest-blue
[doc-url]: https://repositony.github.io/ntools_doc/index.html

**A modular toolkit of fast and reliable libraries for neutronics analysis**

The full library documentation is published [here](https://repositony.github.io/ntools_doc/index.html)

***This is a pre-release version for testing and development, so breaking changes will often occur until a stable 1.0 release.***

## Library overview

The `ntools` toolkit contains a collection of mostly modular libraries for
common fusion neutronics tasks and analysis.

| Crate | Description |
| ----- | ----------- |
| [fispact](https://repositony.github.io/ntools_doc/ntools/fispact/index.html) | Analysis tools for FISPACT-II inventory calculations  |
| [iaea](https://repositony.github.io/ntools_doc/ntools/iaea/index.html)       | Module for interacting with the IAEA decay data API   |
| [mesh](https://repositony.github.io/ntools_doc/ntools/mesh/index.html)       | MCNP mesh tally operations and file parsing           |
| [mctal](https://repositony.github.io/ntools_doc/ntools/mctal/index.html)     | MCNP MCTAL file parsing and tally data                |
| [posvol](https://repositony.github.io/ntools_doc/ntools/posvol/index.html)   | Se/deserialiser for UKAEA CuV posvol binaries         |
| [utils](https://repositony.github.io/ntools_doc/ntools/utils/index.html)     | Common utilities and extension traits                 |
| [weights](https://repositony.github.io/ntools_doc/ntools/weights/index.html) | Tools for MCNP weight window operations               |
| [wwgen](https://repositony.github.io/ntools_doc/ntools/wwgen/index.html)     | Weight window generation methods for MCNP             |

[Command line tools](https://github.com/repositony?tab=repositories&q=&type=&language=rust&sort=)
built on these core libraries are maintained in their own repositories.

### Modular crates

The `ntools` crates are included as dependencies through feature flags. Specify
`"full"` to include everything.

```toml
[dependencies]
# via SSH
ntools = { git = "ssh://git@github.com/repositony/ntools.git", features = ["full"] }

# via HTTPS
ntools = { git = "https://github.com/repositony/ntools.git", features = ["full"] }
```

It is recommended that users are more selective to avoid compiling unnecessary
dependencies.

For example, if only the `fispact` and `iaea` crates are needed:

```toml
[dependencies]
# via SSH
ntools = { git = "ssh://git@github.com/repositony/ntools.git", features = ["fispact", "iaea"] }

# via HTTPS
ntools = { git = "https://github.com/repositony/ntools.git", features = ["fispact", "iaea"] }
```

### Documentation and Tests

To reproduce the full library documentation seen
[here](https://repositony.github.io/ntools_doc/index.html):

```shell
cargo doc --workspace --no-deps --features full
```

To run all tests for all modules, use the `--workspace` flag.

```shell
cargo test --workspace
```
