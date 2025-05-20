## Setup local development environment on macOS

- #### [Core packages](#core-packages)
- #### [Colima](#colima-as-an-alternative-to-docker-desktop)
- #### [NeoVim packages](#neovim-packages)
- #### [NeoVim configuration structure](#neovim-configuration-structure)

---
#### Core packages
- install [Homebrew](https://github.com/Homebrew/brew) package manager
```shell
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
- install [Ghostty](https://github.com/ghostty-org/ghostty) terminal emulator
```shell
brew install --cask ghostty
```
---
#### NeoVim packages
- install dependencies [ripgrep](https://github.com/BurntSushi/ripgrep) and [fd](https://github.com/sharkdp/fd)
```shell
brew install ripgrep fd
```
- install [NeoVim](https://github.com/neovim/neovim) editor
```shell
brew install neovim
```
- install languages servers: [Lua](https://github.com/LuaLS/lua-language-server), [PHP](https://github.com/bmewburn/vscode-intelephense)
```shell
brew install lua-language server
npm i intelephense -g
```
---
#### Colima as an alternative to Docker Desktop
- uninstall [Docker Desktop](https://docs.docker.com/desktop/uninstall/), find leftovers in your system and remove them
```shell
find . -name '*docker*'
```
- install [Docker CLI](https://github.com/docker/cli)
```shell
brew install docker
```
- install [Docker Compose](https://github.com/docker/compose)
```shell
brew install docker-compose
```
- optionally, install [Docker Buildx](https://github.com/docker/buildx)
```shell
brew install docker-buildx
```
- if you need a Kubernetes cluster, install [Kubernetes CLI](https://github.com/kubernetes/kubernetes)
```shell
brew install kubernetes-cli
```
- install [Colima](https://github.com/abiosoft/colima)
```shell
brew install colima
```
- start Colima and create a new virtual machine
> [!NOTE]
> a new machine will be created with 4 CPU, 4Gb RAM, 64Gb disk size and based on Apple Virtualization framework
```shell
colima start --cpu 4 --memory 4 --disk 64 --vm-type=vz --mount-type=virtiofs
```
- to run it together with k8s
```shell
colima start --kubernetes
```
- ...or without later
```shell
colima start --kubernetes=false
```
---
#### NeoVim configuration structure

[nvim](https://github.com/oleksiivelychko/dotfiles/nvim)<br>
---- [lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua)<br>
-------- [me](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me)<br>
------------ [custom](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom)<br>
---------------- [ui](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/ui)<br>
-------------------- [colors.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/ui/colors.lua)<br>
-------------------- [icons.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/ui/icons.lua)<br>
---------------- [init.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/init.lua)<br>
---------------- [keymap.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/keymap.lua)<br>
---------------- [options.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/options.lua)<br>
---------------- [styles.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/custom/styles.lua)<br>
------------ [plugins](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins)<br>
---------------- [lspls](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/lspls)<br>
-------------------- [intelephense.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/lspls/intelephense.lua)<br>
-------------------- [luals.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/lspls/luals.lua)<br>
---------------- [cmp.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/cmp.lua)<br>
---------------- [colorscheme.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/colorscheme.lua)<br>
---------------- [git.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/git.lua)<br>
---------------- [init.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/init.lua)<br>
---------------- [kulala.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/kulala.lua)<br>
---------------- [lsp.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/lsp.lua)<br>
---------------- [statusline.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/statusline.lua)<br>
---------------- [telescope.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/telescope.lua)<br>
---------------- [tree.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/tree.lua)<br>
---------------- [treesitter.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/plugins/treesitter.lua)<br>
------------ [lazy.lua](https://github.com/oleksiivelychko/dotfiles/nvim/lua/me/lazy.lua)<br>
---- [init.lua](https://github.com/oleksiivelychko/dotfiles/nvim/init.lua)<br>
---- [lazy-rock.json](https://github.com/oleksiivelychko/dotfiles/nvim/lazy-rock.lua)<br>

---
