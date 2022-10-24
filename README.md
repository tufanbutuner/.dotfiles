## Steps to bootstrap a new Mac

Install Apple's Command Line Tools, which are prerequisites for Git and Homebrew.
```
xcode-select --install
```
Clone repo into new hidden directory.
```
# Use SSH (if set up)...
    git clone git@github.com:eieioxyz/Beyond-Dotfiles-in-100-Seconds.git ~/.dotfiles
```
Create symlinks in the Home directory to the real files in the repo.

```
# There are better and less manual ways to do this;
# investigate install scripts and bootstrapping tools.

ln -s ~/.dotfiles/.zshrc ~/.zshrc
ln -s ~/.dotfiles/.gitconfig ~/.gitconfig
```
Install Homebrew, followed by the software listed in the Brewfile.
```
# These could also be in an install script.

# Install Homebrew
    /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# Then pass in the Brewfile location...
    brew bundle --file ~/.dotfiles/Brewfile

# ...or move to the directory first.
    cd ~/.dotfiles && brew bundle
```