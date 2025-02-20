# dotfiles

Personal and work dotfiles setup using [chezmoi](https://www.chezmoi.io/).

To setup a new device, from the home directory run:

```shell
sudo apt install zsh unzip
chsh -s /bin/zsh
sh -c "$(curl -fsLS get.chezmoi.io)" -- init --apply rneacsu --purge-binary
mkdir -p ~/.config/local/share
mv ~/.local/share/chezmoi ~/.config/local/share
rm -r ~/bin ~/.local
```
