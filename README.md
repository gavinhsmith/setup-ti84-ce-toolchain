# setup-ti84-ce-toolchain

GitHub Action that installs the [CE C/C++ toolchain](https://github.com/CE-Programming/toolchain) for building TI-84 Plus CE calculator programs in CI.

## Usage

```yaml
- uses: gavinhsmith/setup-ti84-ce-toolchain@v1
  with:
    version: v14.2 # optional, defaults to v14.2
```

`ez80-clang` and the rest of the toolchain are on `PATH` and `CEDEV` is set — just run `make` after this step.

## Inputs

| Input          | Default       | Description                                       |
| -------------- | ------------- | ------------------------------------------------- |
| `version`      | `v14.2`       | A toolchain release tag, or `latest` / `nightly`. |
| `install-path` | `$HOME/CEdev` | Where to install CEdev.                           |

## Outputs

| Output       | Description                          |
| ------------ | ------------------------------------ |
| `cedev-path` | Absolute path to the installed CEdev |

> v15.0+ dropped the fasmg assembler for GNU binutils/GAS. Stay on a `v14.x` tag until any `.asm` sources are migrated to `.s`/`.S`.
