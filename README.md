# :diamond_shape_with_a_dot_inside: git_bridge_wsl2_and_windows :diamond_shape_with_a_dot_inside:

A workaround for too heavy working of WSL2 git on NTFS by git.exe.

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
