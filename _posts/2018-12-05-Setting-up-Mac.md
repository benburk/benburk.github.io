---
layout: post
title: Setting up Mac for Development
---

How to set up mac for development.

# Mac Setup
After purging or buying a Mac, you should...

## System Preferences

### Trackpad
- Secondary click → Click in bottom right corner
- Tap to click

### Dock
- Automatically hide and show the dock
- Don’t show recent apps

### Keyboard
- Shortcuts -> Mission Control -> ^n to switch to desktop n
- Text -> disable auto correct
- Dictation -> Shortcut -> Right command key twice (fn key used as hyper in karabiner)

### Accesibility
- Zoom -> Use scroll gesture with modifier keys

## Safari
- Extensions: bitwarden, wipr, hoverzoom, vimari
- Settings -> General -> Uncheck "open safe files after downloading"

## Finder
- General -> new finder window shows “Dropbox”
- View -> Customize toolbar -> remove everything :)
- Advanced -> Check “Show all filename extensions”

## Security
https://blog.bejarano.io/hardening-macos.html


## Terminal
- install Nord theme

## Homebrew and command line tools
Homebrew now installs command line tools for you? otherwise xcode-select —install

## Fish Shell
    brew install fish
    echo "/usr/local/bin/fish" | sudo tee -a /etc/shells
    chsh -s /usr/local/bin/fish
    fish_config
    set -U fish_user_paths /anaconda3/bin $fish_user_paths

## Homebrew Packages
    octave, youtube-dl, git

## Homebrew Casks
    karabiner-elements, dropbox, visual-studio-code, iina

## Python
    brew cask install anaconda
    pip install black, pylint
    conda install pytorch

## Visual Studio Code Extensions
    vim, python, nord-theme

## Update stuff
App Store -> Check for updates
brew upgrade

