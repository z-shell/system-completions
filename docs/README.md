<h1 align="center">
  <a href="https://github.com/z-shell/zi"><p>
    <img align="center" src="https://github.com/z-shell/zi/raw/main/docs/images/logo.svg" alt="Zi Logo" width="60px" height="60px" />
  </a>❮ Zi ❯ Package - System Completions </p>
</h1>
<h2 align="center">
  <p> Moves the stock Zsh completions under the control of Zi and provides the ability to selectively enable (<code>cenable</code>) / disable (<code>cdisable</code>).</p>
</h2>
<h3 align="center">
<table>
    <tr>
        <td><b>Package source:</b></td>
        <td>Tarball</td>
        <td>Binary</td>
        <td>Git</td>
        <td>Node</td>
        <td>Gem</td>
        <td>Mod</td>
    </tr>
    <tr>
        <td><b>Status:</b></td>
        <td>❌</td>
        <td>❌</td>
        <td>❌</td>
        <td>❌</td>
        <td>❌</td>
        <td>✔️ (default)</td>
    </tr>
</table></h3>
<p><img align="center" src="https://user-images.githubusercontent.com/59910950/161076706-03d6fb67-e8a2-41ce-a6a8-f19db27b2ecb.png" alt="zi zsh system-completions package" width="100%" height="auto" /></p><hr />

## Available `pack''` invocations

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

```shell
# Utilize Turbo and initialize the completion with fast compinit
zi wait pack atload=+"zicompinit_fast; zicdreplay" for system-completions
```

The **Zi** command executed will be equivalent to:

```shell
zi id-as=system-completions wait as=completion lucid \
  atclone="+zi-message 'Installing system completions...'; \
    command mkdir -p ${ZPFX}/completions; \
    command cp -f ${ZPFX}/share/zsh/${ZSH_VERSION}/functions/^_* ${ZPFX}/completions; \
    zi creinstall -q ${ZPFX}/share/zsh/${ZSH_VERSION}/functions;" \
  atload="fpath=( ${(u)fpath[@]:#${ZPFX}/share/zsh/*} ); fpath+=( ${ZPFX}/completions );" \
  atpull="%atclone" run-atpull nocompile countdown for \
    z-shell/0
```

---

> This repository compatible with [**Zi**](https://github.com/z-shell/zi)

The [**Zi**](https://github.com/z-shell/zi) zsh package that uses the [zsh-string-lib](https://github.com/z-shell/zsh-string-lib) to automatically:

- get the plugin's Git repository OR release-package URL,
- get the list of the recommended ices for the plugin,
  - there can be multiple lists of ices,
  - the ice lists are stored in _profiles_; there's at least one profile, _default_,
  - the ices can be selectively overridden.
