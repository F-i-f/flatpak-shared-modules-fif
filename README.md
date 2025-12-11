This repository contains commonly shared modules and is intended to be used as a git submodule.
Note that it includes the [FlatHub shared-modules](https://github.com/flathub/shared-modules)
as a git submodule.

To use shared modules for packaging an application, add the submodule:

```
git submodule add https://github.com/F-i-f/flatpak-shared-modules-fif.git shared-modules-fif
git submodule update --init --recursive
```

Then modules from this repository can be specified in a manifest JSON file like this:

```json
"modules": [
  "shared-modules-fif/zsh/zsh-build.json",
  {
    "name": "zsh-build"
  }
]
```

To update the submodule:

```
git submodule update --remote --merge --recursive
```

To remove the submodule:

```
git submodule deinit -f -- shared-modules-fif
rm -rf .git/modules/shared-modules-fif
git rm -f shared-modules-fif
rm .gitmodules
```

This document is based upon [FlatHub's `shared-modules`
README.md](https://github.com/flathub/shared-modules/blob/master/README.md).
