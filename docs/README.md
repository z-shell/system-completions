<div align="center"><table align="center">
  <tr><td align="center">
    <h1 align="center">
      <a href="https://github.com/z-shell/zi">
        <img align="center" src="https://github.com/z-shell/zi/raw/main/docs/images/logo.svg" alt="Logo" width="80" height="80" />
      </a>
      ❮ ZI ❯ Package - System Completions
    </h1><h2>

| **Package source:** | Tarball | Binary | Git | Node | Gem |        Mod         |
| :-----------------: | :-----: | :----: | :-: | :--: | :-: | :----------------: |
|     **Status:**     |   :x:   |  :x:   | :x: | :x:  | :x: | :heavy_check_mark: |

</h2><h3> Generates table of contents for markdown files inside local git repository. </h3>
<p><img align="center" src="https://user-images.githubusercontent.com/59910950/161076706-03d6fb67-e8a2-41ce-a6a8-f19db27b2ecb.png" alt="zi zsh system-completions package" width="100%" height="auto" /></p>
</td></tr></table></div>

## Available `pack''` invocations

Moves the stock Zsh completions under the control of ZI. You can then selectively enable and disable the completions with `cenable` and `cdisable`.

### Default Profile

```shell
zi pack for system-completions
```

```shell
# Utilize Turbo
zi wait pack for system-completions
```

```shell
# Utilize Turbo and initialize the completion system
zi wait pack atload=+"zicompinit; zicdreplay" for system-completions
```

The ZI command executed will be equivalent to:

```shell
zi id-as=system-completions wait as=completion lucid \
  atclone='print Installing system completions...; \
    mkdir -p $ZPFX/funs; \
    command cp -f $ZPFX/share/zsh/$ZSH_VERSION/functions/^_* $ZPFX/funs; \
    zi creinstall -q $ZPFX/share/zsh/$ZSH_VERSION/functions' \
      atload='fpath=( ${(u)fpath[@]:#$ZPFX/share/zsh/*} ); fpath+=( $ZPFX/funs )' \
        atpull="%atclone" nocompile run-atpull for \
          z-shell/null
```

---

> This repository compatible with [ZI](https://github.com/z-shell/zi)

The [ZI](https://github.com/z-shell/zi) zsh package that can use the [zsh-string-lib](https://github.com/z-shell/zsh-string-lib) to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.
