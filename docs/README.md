
<div align="center"><table style="width:100%;height:auto">
<tr><td align="center">
<a title="ZI" target="_self" href="https://github.com/z-shell/zi/">
<h2><img align="center" style="width:60px;height:auto" src="https://github.com/z-shell/zi/raw/main/docs/images/logo.svg" alt="ZI Logo" /></a>
❮ ZI ❯ Package - System Completions </h2><h3> Builds and installs the newest Zsh (HEAD of the Git repository).</h3>
</td></tr>
<tr><td align="center"><h3>

| **Package source:** | Tarball | Binary | Git | Node | Gem | Mod |
| :-----------------: | :-----: | :----: | :-: | :--: | :-: | :-: |
|     **Status:**     |   :x:   |  :x:   | :x: | :x:  | :x: | :heavy_check_mark: |

</h3>
  <img style="width:90%;height:auto" alt="z-shell_system-completions" src="https://user-images.githubusercontent.com/59910950/161076706-03d6fb67-e8a2-41ce-a6a8-f19db27b2ecb.png">
</td></tr></table></div>

## Available `pack''` invocations

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

---

> This repository compatible with [ZI](https://github.com/z-shell/zi)

The [ZI](https://github.com/z-shell/zi) zsh package that can use the NPM package registry to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.
