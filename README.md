# R version switcher for macOS


## Installation

```bash
mkdir -p ~/bin
curl -L https://raw.githubusercontent.com/klmr/switch-r/main/switch-r >~/bin/switch-r
chmod +x ~/bin/switch-r
```

Next, ensure that `~/bin` is on your `PATH` — or copy the script to a location
that is.

## Usage

```bash
⟩⟩⟩ switch-r --help
/Users/konrad/bin/switch-r [--list|--current|‹version›]

⟩⟩⟩ switch-r -l # or --list
· 3.5
· 3.6
✔︎ 4.0
· 4.1
```

switch-r only looks for R versions installed as a framework via the original
pkg, either from [r-project.org](https://r-project.org/), or via `brew install
--cask r`. Other installed versions of R are ignored.

The script works by switching the `Current` symlink under
`/Library/Frameworks/R.framework/Versions/` to the specified framework version.
This requires that the R library path includes the R version (e.g. [by setting
`R_LIBS_USER` to contain
`%v`](https://stat.ethz.ch/R-manual/R-devel/library/base/html/libPaths.html)),
otherwise loading packages may not work.
