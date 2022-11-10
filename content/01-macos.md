+++
title = "Bootstrapping macOS for development"
date = 2022-01-07
+++

This post provides an overview of how I configure my mac for development and general use. I use this for my own personal reference, and share it here to provide ideas for others.

# Starting fresh
I like to factory reset my computer once a year to
- test my backup strategies
- consider which tools and applications I still like using in my workflow
- clear out loose files and cruft that have accumulated on my system
- make the computer feel like new

macOS Monterey made it easier to reset a Mac using the "Erase All Content and Settings" feature. [Apple Guide](https://support.apple.com/en-ca/HT212749)

# Command line tools
First, we install macOS command line tools. This package enables UNIX-style development via Terminal by installing command line developer tools, such as the Apple LLVM compiler, linker, and Make. The full set of tools exists in this folder `/Library/Developer/CommandLineTools/usr/bin/`. It also includes macOS SDK frameworks and headers.

```bash
xcode-select --install
```


# Zsh
Since macOS Catalina, `zsh` comes installed as the default shell. I use [Oh-my-zsh](https://ohmyz.sh) for plugins.
```bash
# 1. Install oh-my-zsh (https://ohmyz.sh/#install)
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# 2. Download zsh plugins
git clone https://github.com/zsh-users/zsh-autosuggestions.git $ZSH_CUSTOM/plugins/zsh-autosuggestions
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git $ZSH_CUSTOM/plugins/zsh-syntax-highlighting
```

# Homebrew

Homebrew isn't without its flaws, but remains one of the better and most popular package managers one can use on a Mac. Homebrew allows one to install command line tools as well as GUI applications using `--casks`. It also provides a convenient way of upgrading and uninstalling applications.
```bash
# 1. Install homebrew (https://brew.sh)
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"

# 2. Install some additional command line tools
brew install rg fd fzf git vale helix
/usr/local/opt/fzf/install  # fzf setup

# Quick-look plugins https://www.quicklookplugins.com
brew install --cask qlcolorcode qlstephen

# Applications
brew install --cask 1password karabiner-elements telegram visual-studio-code iina qbittorrent obsidian logisim-evolution selfcontrol nordvpn cryptomator
```

# Rust
```bash
# https://www.rust-lang.org/tools/install
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh

# Install formatting tool
rustup component add rustfmt
```

# Python
If you need more than one Python version installed, consider using `pyenv`.
```bash
brew install python

# dependencies I like
pip install "black==22.8.0" "isort==5.10.1" "mypy==0.971" "pylint==2.15.3" "pytest==7.1.3" "pytest-cov==3.0.0" "refurb"
```

# Dotfiles
At one point, I tried to make everything work out of `$XDG_CONFIG_HOME`. Inevitably one tool wouldn't respect it (e.g. ) and break the convention. I have since just opted to define my own dotfile structure and then symlink the files to their appropriate locations.

Some people choose to use [programs](https://wiki.archlinux.org/title/Dotfiles#Tools) to manage this but I appreciate the simplicity of my current setup.

```bash
mkdir ~/dotfiles
git clone https://github.com/benburk/dotfiles ~/dotfiles
./dotfiles/install_dotfiles
```


# System preferences
The `defaults` command can configure these preferences programmatically. I might move to that. [Example](https://github.com/mathiasbynens/dotfiles/blob/master/.macos)

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
Paid extensions downloaded via App Store: SponsorBlock, and Wipr.
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


# iOS
- Apps: Obsidian, Fastmail, WolframAlpha

# Further reading
- [Hardening macOS](https://blog.bejarano.io/hardening-macos.html)
- [macOS setup guide](https://sourabhbajaj.com/mac-setup/)
- [Ask HN: What feature did you find after years of using macOS? (2020)](https://news.ycombinator.com/item?id=24091707)
- [Making macOS behave itself](https://danmackinlay.name/notebook/macos_hacks.html)