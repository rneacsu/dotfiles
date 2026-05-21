# dotfiles

Personal and work dotfiles setup using [chezmoi](https://www.chezmoi.io/) and [mise](https://mise.jdx.dev/)

To setup a new device, from the home directory run:

```shell
sudo apt install zsh unzip git curl
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
mise i
```

Then restart the shell and you should be good to go.

## GPG on MacOS

To use the `gpg --card-status` and `gpg --card-edit` commands, add the following to `scdaemon.conf`:

```
pcsc-shared
```
This disables the pin and password caching, so make sure to remove the option once you are done using the commands.

In case the card is not detected, try the following:

```shell
gpgconf --kill scdaemon
gpgconf --kill gpg-agent
pcsctest
```
