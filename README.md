# dotfiles

Personal and work dotfiles setup using [chezmoi](https://www.chezmoi.io/) and [mise](https://mise.jdx.dev/)

To setup a new device, from the home directory run:

```shell
sudo apt install zsh unzip
chsh -s /bin/zsh

export XDG_CONFIG_HOME="$HOME/.config"
export XDG_DATA_HOME="$XDG_CONFIG_HOME/local/share"
export XDG_STATE_HOME="$XDG_CONFIG_HOME/local/state"
export XDG_RUNTIME_DIR="$XDG_CONFIG_HOME/local/runtime"
export XDG_CACHE_HOME="$XDG_CONFIG_HOME/cache"
export XDG_BIN_HOME="$XDG_DATA_HOME/bin"
path+=($XDG_BIN_HOME)

curl https://mise.run | MISE_INSTALL_PATH=${XDG_BIN_HOME}/mise sh
mise x chezmoi -- chezmoi init --apply rneacsu
```
