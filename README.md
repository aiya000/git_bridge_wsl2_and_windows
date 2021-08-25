# :diamond_shape_with_a_dot_inside: git_bridge_wsl2_and_windows :diamond_shape_with_a_dot_inside:

A workaround for too heavy working of WSL2 git on NTFS by git.exe.

## Purpose

Unfortunately, current WSL2 git with git repositories on NTFS is much slower.

- That problem's detail: [filesystem performance is much slower than wsl1 in /mnt - microsoft/WSL](https://github.com/microsoft/WSL/issues/4197)

This repo solves that problem by bridging between WSL2's git and git.exe (git for Windows) :+1::sparkles:

## Installation

```shell-session
$ git clone https://github.com/aiya000/git_bridge_wsl2_and_windows \
    path/to/somewhere/git_bridge_wsl2_and_windows

$ mkdir ~/bin           # Or a directory you like
$ PATH=$HOME/bin:$PATH  # Should heading than /usr/bin

$ ln -s path/to/somewhere/git_bridge_wsl2_and_windows/git_bridge_wsl2_and_windows ~/bin/git

# Now this is working well with you :D
```

## Requirements

- WSL2
- WSL2 git (`apt install git`)
- [git for windows](https://gitforwindows.org)
    - Please also add this into your `$PATH` too

## Options
### Environment variables

- `$GIT_BRIDGE_WSL2_AND_WINDOWS_DEBUG`
    - default: `0`

```shell-session
$ GIT_BRIDGE_WSL2_AND_WINDOWS_DEBUG=1 git status
git_bridge_wsl2_and_windows: Using WSL2 git
git_bridge_wsl2_and_windows: is_needing_auth: false
git_bridge_wsl2_and_windows: should_use_windows_git: false
git_bridge_wsl2_and_windows: /usr/bin/git status
## main...origin/main [ahead 3]
...
```

- `$GIT_BRIDGE_WSL2_AND_WINDOWS_GIT_WSL2`
    - default: `/usr/bin/git`
- `$GIT_BRIDGE_WSL2_AND_WINDOWS_GIT_WINDOWS`
    - default: `git.exe`

```shell-session
$ GIT_BRIDGE_WSL2_AND_WINDOWS_GIT_WSL2=/usr/local/bin/git git status
```
