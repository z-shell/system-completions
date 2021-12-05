<h3>

| **Package source:** | Tarball | Binary | Git | Node | Gem |
| :-----------------: | :-----: | :----: | :-: | :--: | :-: |
|     **Status:**     |   :x:   |  :x:   | :x: | :x:  | :x: |

</h3>

- [Introduction](#introduction)
- [Install](#install)
  - [Available `pack''` invocations](#available-pack-invocations)
  - [Default Profile](#default-profile)

## Introduction

> **[?]**
> This repository not compatible with previous versions (zplugin, zinit).
>
> Please upgrade to [ZI](https://github.com/z-shell-zi)

The [ZI](https://github.com/z-shell-zi) zsh package that can use the NPM package registry to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.

## Install

### Available `pack''` invocations

Moves the stock Zsh completions under the control of ZI. You can then
selectively enable and disable the completions with `cenable` and `cdisable`.

Example ZI invocations:

```zsh
zi pack for system-completions

# Utilize Turbo
zi wait pack for system-completions

# Utilize Turbo and initialize the completion system
zi wait pack atload=+"zicompinit; zicdreplay" for system-completions
```

### Default Profile

The ZI command executed will be equivalent to:

```zsh
zi id-as=system-completions wait as=completion lucid \
    atclone='print Installing system completions...; \
      mkdir -p $ZPFX/funs; \
      command cp -f $ZPFX/share/zsh/$ZSH_VERSION/functions/^_* $ZPFX/funs; \
      zi creinstall -q $ZPFX/share/zsh/$ZSH_VERSION/functions' \
    atload='fpath=( ${(u)fpath[@]:#$ZPFX/share/zsh/*} ); \
      fpath+=( $ZPFX/funs )' \
    atpull="%atclone" run-atpull for \
         z-shell/null
```
