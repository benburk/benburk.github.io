+++
title = "Bootstrapping macOS for development"
date = 2022-01-07
+++

This is an overview of how I configure my mac for my workflow. I do software development in Rust and Python, write notes, and browse the web. 

# Starting fresh

I try to factory reset my laptop once a year in order to:
- test and evaluate my backup strategies
- evaluate my workflow and tools I use to keep it simple
- make the computer feel like new
- clear out loose files that get sprawled across OS

Since Monterey, it is quite easy using Erase All Content and Settings in System Preferences. [Apple Guide](https://support.apple.com/en-ca/HT212749)


# Zsh

Zsh is the default shell in macOS since Catalina. I used to use Fish, but I find I'm able to get most of what I liked about it through Zsh plugins.

```bash
# https://ohmyz.sh/#install
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# Download zsh plugins
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

# Homebrew

Homebrew isn't without its flaws but overall remains one of the better package managers one can use on a mac.

```bash
# https://brew.sh
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# essential tools
brew install rg fd fzf
/usr/local/opt/fzf/install  # fzf setup

# quick look plugins https://www.quicklookplugins.com
brew install --cask qlcolorcode qlstephen
```

# Applications

From the App Store I download 1Password, Telegram, Wipr, NordVPN.

```bash
brew install --cask karabiner-elements visual-studio-code iina qbittorrent obsidian
```

# Rust

```bash
# https://www.rust-lang.org/tools/install
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
rustup component add rustfmt
```

# Python

Not completely decided on whether to install python from homebrew or the [website installer](https://www.python.org/downloads/)

```bash
brew install python
```

- Poetry
- invoke + tasks.py


# Dotfiles

At one point I tried to make everything work out of `$XDG_CONFIG_HOME`. Inevitably one tool wouldn't respect it and break the convention. I have since just opted to define my own structure and then symlink the files to their appropriate locations.

Some people choose to use [programs](https://wiki.archlinux.org/title/Dotfiles#Tools) to manage this but I appreciate the simplicity of my current setup.

```bash
mkdir ~/dotfiles
git clone https://github.com/benburk/dotfiles ~/dotfiles
./dotfiles/install_dotfiles
```


# System preferences

These can be set using defaults commands. I might move to that. [Example](https://github.com/mathiasbynens/dotfiles/blob/master/.macos)

## Finder
```
General -> New Finder windows show -> SynologyDrive
Sidebar -> Show home directory
Sidebar -> Hide Recents, Documents
Advanced -> Show filename extensions
Advanced -> Don't show warning before changing an extension
Advanced -> Don't show warning before removing from iCloud Drive
Advanced -> Don't show warning before emptying trash
Advanced -> Keep folders on top when sorting by name
Advanced -> When performing a search: Search the current folder
```

## Safari
```
General -> Don't open safe files after downloading
Tabs -> Tab Layout -> Compact
Autofill -> Disable all
Search -> Search engine -> DuckDuckGo
```

## Terminal
```
Download nord theme from https://github.com/arcticicestudio/nord-terminal-app
Profiles -> Import -> Nord.terminal
Nord profile -> Set default
Keyboard -> Use Option as Meta key
```

## System preferences
```
Dock & Menu Bar
- Automatically hide and show the Dock
- Don't show recent applications in Dock
- Battery -> Show percentage
- Clock -> Display the time with seconds
- Spotlight -> Don't show in menu bar
- Siri -> Don't show in menu bar

Mission Control
- Don't Automatically rearrange Spaces based on most recent use

Spotlight
- Enable Applications, Calculator, Conversion, Definition, Music

Keyboard
- Press Globe -> Do Nothing
- Touch Bar shows -> Expanded Control Strip
- Text -> Disable autocorrect, smart quotes, and dashes
- Shortcuts -> Mission Control -> Switch to Desktop 1-9

Trackpad
- Point & Click -> Secondary click -> Click in bottom right corner
- Point & Click -> Tap to click -> Click with one finger
```


# Further reading

- [Hardening macOS](https://blog.bejarano.io/hardening-macos.html)
- [macOS setup guide](https://sourabhbajaj.com/mac-setup/)
- [Ask HN: What feature did you find after years of using macOS? (2020)](https://news.ycombinator.com/item?id=24091707)
- [Making macOS behave itself](https://danmackinlay.name/notebook/macos_hacks.html)