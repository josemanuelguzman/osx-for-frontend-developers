# OS X for Front-end developers <!-- omit in toc -->

As Front-end developers 🤓 we can build basic websites with nothing more than a text editor and a browser, but we want to up our game by adding a JavaScript framework like React or Vue and useful tools like Git to our workflow.

But wait! Our Mac isn’t ready. Before diving in, we’ll need to install a few items that will save we from confusing errors later. 😩

This is the minimum (IMO) setup we'll need to get up and run on our Mac and a checklist to set up our ✨ OS X for front-end development.

🚀 Let’s go!

### Table of Contents <!-- omit in toc -->

- [🛡️ Security](#️-security)
  - [Update Your Mac](#update-your-mac)
  - [Enable Firewall](#enable-firewall)
  - [Enable FileVault Encryption](#enable-filevault-encryption)
- [💻 System Tweaks](#-system-tweaks)
  - [Unhide the Library folder](#unhide-the-library-folder)
  - [Show Path Bar and Status Bar in Finder](#show-path-bar-and-status-bar-in-finder)
  - [Show Full Path in Finder Title Bar](#show-full-path-in-finder-title-bar)
  - [Prevent Time Machine from Prompting to Use New Hard Drives as Backup Volume](#prevent-time-machine-from-prompting-to-use-new-hard-drives-as-backup-volume)
  - [Show All File Extensions](#show-all-file-extensions)
  - [Disable Creation of DS_Store Files on Network Volumes and USB Drives](#disable-creation-of-ds_store-files-on-network-volumes-and-usb-drives)
- [🛠️ Command Line Developer Tools](#️-command-line-developer-tools)
- [🍺 Homebrew](#-homebrew)
- [⬛ Choose a Terminal App](#-choose-a-terminal-app)
- [👨🏻‍💻 Dev apps](#-dev-apps)
  - [Curl](#curl)
  - [Docker](#docker)
  - [Elasticsearch](#elasticsearch)
  - [Findutils](#findutils)
  - [Firefox](#firefox)
  - [Arc](#arc)
  - [Fonts](#fonts)
    - [Font Jetbrains Mono](#font-jetbrains-mono)
    - [Font Fira Code](#font-fira-code)
  - [Git](#git)
  - [Git flow](#git-flow)
  - [Google Chrome](#google-chrome)
  - [GnuPG](#gnupg)
  - [GNU sed](#gnu-sed)
  - [GNU tar](#gnu-tar)
  - [Grep](#grep)
  - [Imagemagick](#imagemagick)
  - [iTerm2](#iterm2)
  - [Warp](#warp)
  - [Java Runtime](#java-runtime)
  - [MongoDB](#mongodb)
  - [MySQL](#mysql)
  - [Ngrok](#ngrok)
  - [Nodejs](#nodejs)
  - [NVM](#nvm)
  - [Bun](#bun)
  - [pnpm](#pnpm)
  - [Vite](#vite)
  - [esbuild](#esbuild)
  - [TypeScript](#typescript)
  - [Vitest](#vitest)
  - [Playwright](#playwright)
  - [oh-my-zsh](#oh-my-zsh)
  - [Perl](#perl)
  - [Postgresql](#postgresql)
  - [Python](#python)
  - [Rainbarf](#rainbarf)
  - [Redis](#redis)
  - [Ruby](#ruby)
  - [RVM](#rvm)
  - [SASS](#sass)
  - [Tailwind CSS](#tailwind-css)
  - [PostCSS](#postcss)
  - [Turborepo](#turborepo)
  - [Nx](#nx)
  - [Tmux](#tmux)
  - [Tmuxinator](#tmuxinator)
  - [TOR](#tor)
  - [PHP](#php)
  - [Postman](#postman)
  - [Bruno](#bruno)
  - [SourceTree](#sourcetree)
  - [Vagrant](#vagrant)
    - [Keep VirtualBox Guest Additions updated](#keep-virtualbox-guest-additions-updated)
  - [VirtualBox](#virtualbox)
  - [Visual Studio Code](#visual-studio-code)
  - [X11](#x11)
  - [Yarn](#yarn)
  - [ZSH](#zsh)
- [👨🏻‍🎨 Designer apps](#-designer-apps)
  - [Figma](#figma)
  - [Sketch](#sketch)
  - [InVision](#invision)
- [🧰 Really useful apps](#-really-useful-apps)
  - [Dropbox](#dropbox)
  - [Google Drive](#google-drive)
  - [Harvest](#harvest)
  - [Notion](#notion)
  - [PoEdit](#poedit)
  - [RectangleApp](#rectangleapp)
  - [Signal](#signal)
  - [Slack](#slack)
  - [Spotify](#spotify)
  - [Telegram](#telegram)
  - [The-unarchiver](#the-unarchiver)
  - [Transmission](#transmission)
  - [VLC](#vlc)
  - [Zoom](#zoom)
- [🗃️ Other stuff](#️-other-stuff)
  - [Update Everything easily](#update-everything-easily)
  - [Zsh prompt for Astronauts. 🤩](#zsh-prompt-for-astronauts-)
    - [Requirements](#requirements)
    - [Installing with oh-my-zsh](#installing-with-oh-my-zsh)
  - [Our privacy matters](#our-privacy-matters)
- [Conclusion](#conclusion)
  - [Credits](#credits)

## 🛡️ Security

✋🏻 First things first!

Keeping your system up to date is crucial. Keep an eye out for updates on the regular.

### Update Your Mac

Before installing any new software, follow [these instructions](https://support.apple.com/HT201541) from Apple to upgrade macOS and your current software to the latest version.

### Enable Firewall

This is for online protection when we're not in our home network or not behind a router.
```bash
sudo /usr/libexec/ApplicationFirewall/socketfilterfw --setglobalstate on
```

### Enable FileVault Encryption

We're most likely using a portable laptop of some kind. If we lose it, the laptop gets stolen or someone tries to hack into it, our personal data is at risk. Using full-disk encryption is an extra layer of security to keep our mind at ease in case of potential intrusion.

🚧 Two main caveats:

- **Do not misplace or forget your FileVault recovery key or login password**. Losing this password means you cannot log in and without the recovery key everything on your computer is inaccessible if you can't decrypt the files during a recovery. iCloud is an option to store the Filevault password. Using iCloud, Apple Support will be able to assist you with recovering data. iCloud isn't fully encrypted so whilt it's convenient, it's less secure.
- If macOS gets corrupted and you need to download files from the drive after accessing the drive from an external case, it's not possible without the password and recovery key. Make sure you're both backing up using [Time Machine](https://support.apple.com/HT201250) on an external drive or a NAS.

Follow [these instructions](https://support.apple.com/HT204837) from Apple to enable FileVault Encryption.

## 💻 System Tweaks

Apple's default system settings are limiting and don't show a lot of information. Let's change the settings for better usability around the system.

### Unhide the Library folder

```bash
chflags nohidden ~/Library
```
    
Alternatively, open Finder, press <kbd>⇧</kbd> <kbd>⌘</kbd> <kbd>H</kbd> , <kbd>⌘</kbd>  <kbd>2</kbd> , <kbd>⌘</kbd> <kbd>J</kbd> and check *Show Library Folder*. Unhiding this folder could be useful for manual backup, but it's not necessary.

### Show Path Bar and Status Bar in Finder

```bash
defaults write com.apple.finder ShowPathbar -bool true
defaults write com.apple.finder ShowStatusBar -bool true
```

### Show Full Path in Finder Title Bar

```bash
defaults write com.apple.finder _FXShowPosixPathInTitle -bool true
```

### Prevent Time Machine from Prompting to Use New Hard Drives as Backup Volume

I don’t use Time Machine. It is better than nothing but not necessary. But keep this on if you have an external drive you use for backups.

```bash
sudo defaults write /Library/Preferences/com.apple.TimeMachine DoNotOfferNewDisksForBackup -bool true
```

### Show All File Extensions

```bash
defaults write -g AppleShowAllExtensions -bool true
```
    
### Disable Creation of DS_Store Files on Network Volumes and USB Drives

```bash
defaults write com.apple.desktopservices DSDontWriteNetworkStores -bool true
defaults write com.apple.desktopservices DSDontWriteUSBStores -bool true
```

## 🛠️ Command Line Developer Tools

The first thing we'll need to install from the command line are our Mac's **command line developer tools**. Installing these now will prevent weird errors later.

Xcode weighs something ~2GB and is useful for the iOS simulator but is not necessary unless you're developing iOS or Mac apps. Good news is Apple provides a way to install only the Command Line Tools, without Xcode.

Using Terminal, install the tools with this command:
```bash
xcode-select --install
```
To check if the tools are already installed, type the following command in your terminal app and hit return:
```bash
xcode-select --version
```

There's not a straightforward way to update Xcode Command Line Tools, so we have to remove the existing tools to reinstall from scratch.

```bash
sudo rm -rf /Library/Developer/CommandLineTools
xcode-select --install
```

## 🍺 Homebrew

Instead of installing the next few tools by going to each tool's website, finding the download page, clicking the download link, unzipping the files, and manually running the installer, we’re going to use [Homebrew](https://brew.sh/) 😍.

Homebrew is a tool that lets us install, update and uninstall software on our Mac from the command line. This is faster and safer than the manual approach and generally makes your development life easier.

Install Homebrew with:
```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## ⬛ Choose a Terminal App

Since you'll be interacting with your Mac using the command line in this article, you'll need a terminal app.

Any of the following are good options:

- [Warp](https://warp.dev) - Modern, AI-powered terminal with IDE-like features (Recommended for 2025)
- [iTerm2](https://iterm2.com)
- [Hyper](https://hyper.is)
- Terminal (the default app that comes with our Mac's)

## 👨🏻‍💻 Dev apps

### Curl

```bash
brew install curl
```

### Docker

```bash
brew install boot2docker
brew install docker-compose
```

### Elasticsearch

```bash
# tap the Elastic Homebrew repository
brew tap elastic/tap
# install the default distribution of Elasticsearch
brew install elastic/tap/elasticsearch-full
```
To have it launched start elasticsearch and restart at login:

```bash
brew services start elasticsearch
```

### Findutils

```bash
brew install findutils
```

### Firefox

```bash
brew install --cask firefox
```

### Arc

Arc is a modern browser built for productivity with features like spaces, split view, and a command bar. It's becoming increasingly popular among developers and designers.

```bash
brew install --cask arc
```

Arc reimagines how browsers should work with features like automatic tab organization, built-in note-taking, and seamless workspace switching.

### Fonts

```bash
brew tap homebrew/cask-fonts
```

#### Font Jetbrains Mono

✨ The best font for developers 😍

```bash
brew install --cask font-jetbrains-mono
```

#### Font Fira Code

```bash
brew install --cask font-fira-code
```

### Git

```bash
brew install git
# GitHub wrapper
brew install gh
```

### Git flow

```bash
brew install git-flow
```

### Google Chrome

```bash
brew install --cask google-chrome
```

### GnuPG

```bash
brew install gnupg
```

### GNU sed

```bash
brew install gnu-sed
```

### GNU tar

```bash
brew install gnu-tar
```

### Grep

```bash
brew install grep
```

### Imagemagick

```bash
brew install imagemagick --disable-openmp --build-from-source
```

### iTerm2

```bash
brew install --cask iterm2
```

### Warp

Warp is a modern, Rust-based terminal with AI-powered features, command palette, and IDE-like capabilities. It's the next generation of terminal apps.

```bash
brew install --cask warp
```

Warp includes features like AI command search, shareable workflows, and intelligent autocomplete, making it an excellent choice for modern development.

### Java Runtime

Follow [https://support.apple.com/HT204036](https://support.apple.com/HT204036)

### MongoDB

```bash
brew tap mongodb/brew
brew install mongodb-community@4.2
```

To have it launched start mongodb/brew/mongodb-community and restart at login:

```bash
brew services start mongodb/brew/mongodb-community
```

### MySQL

```bash
brew install mysql
```
To have it launched start mysql and restart at login:

```bash
brew services start mysql
```

### Ngrok

```bash
brew install --cask ngrok
```

### Nodejs

I recommend you use [NVM](#nvm) instead of

```bash
brew install node
```

### NVM

```bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.37.2/install.sh | bash
```

Running either of the above commands downloads a script and runs it. The script clones the nvm repository to ~/.nvm, and attempts to add the source lines from the snippet below to the correct profile file (`~/.bash_profile`, `~/.zshrc`, `~/.profile`, or `~/.bashrc`).

```bash
export NVM_DIR="$([ -z "${XDG_CONFIG_HOME-}" ] && printf %s "${HOME}/.nvm" || printf %s "${XDG_CONFIG_HOME}/nvm")"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh" # This loads nvm
```

Install latest node

```bash
nvm install node
```

Set default

````bash
nvm use node
````

### Bun

Bun is an incredibly fast all-in-one JavaScript runtime and toolkit designed to replace Node.js. It includes a native bundler, test runner, and npm-compatible package manager.

```bash
brew tap oven-sh/bun
brew install bun
```

Or using the official installer:

```bash
curl -fsSL https://bun.sh/install | bash
```

Bun is significantly faster than Node.js for many operations and is becoming increasingly popular for modern frontend development.

### pnpm

pnpm is a fast, disk space efficient package manager that's becoming the preferred choice for many modern projects and monorepos.

```bash
brew install pnpm
```

Or using npm:

```bash
npm install -g pnpm
```

pnpm creates a non-flat node_modules structure that saves disk space and resolves dependency issues that npm and yarn sometimes face.

### Vite

Vite is a next-generation frontend build tool that provides an extremely fast dev server and optimized builds. It's become the go-to choice for modern React, Vue, and Svelte projects.

```bash
npm install -g vite
# or with pnpm
pnpm install -g vite
```

You can also create projects directly:

```bash
npm create vite@latest
# or
pnpm create vite
```

Vite's speed comes from using native ES modules during development and esbuild for pre-bundling dependencies.

### esbuild

esbuild is an extremely fast JavaScript bundler and minifier written in Go. It's used under the hood by Vite and other modern tools.

```bash
npm install -g esbuild
# or with pnpm
pnpm install -g esbuild
```

esbuild can be 10-100x faster than traditional bundlers like Webpack, making it ideal for modern development workflows.

### TypeScript

TypeScript has become the de facto standard for modern frontend development. It adds static typing to JavaScript, catching errors early and improving code quality.

```bash
npm install -g typescript
# or with pnpm
pnpm install -g typescript
```

You can also install tsx for running TypeScript files directly:

```bash
npm install -g tsx
# or with pnpm
pnpm install -g tsx
```

TypeScript is now used by default in most modern frameworks and is essential for large-scale frontend applications.

### Vitest

Vitest is a blazing-fast unit test framework powered by Vite. It's become the preferred testing solution for modern frontend projects.

```bash
npm install -g vitest
# or with pnpm
pnpm install -g vitest
```

Vitest provides a Jest-compatible API with better performance and native ESM support, making it ideal for Vite-based projects.

### Playwright

Playwright is a modern end-to-end testing framework that supports all major browsers. It's become the industry standard for reliable E2E testing.

```bash
npm install -g @playwright/test
# or with pnpm
pnpm install -g @playwright/test
```

After installation, initialize Playwright:

```bash
npm init playwright@latest
```

Playwright offers better reliability, faster execution, and more features compared to alternatives like Selenium or Puppeteer.

### oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.github.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```

### Perl

```bash
brew install perl
```

### Postgresql

```bash
brew install postgresql
```
To have it launched start postgresql and restart at login:

```bash
brew services start postgresql
```

### Python

```bash
brew install python
```

### Rainbarf

```bash
brew install rainbarf
```

### Redis

```bash
brew install redis
```
To have it launched start redis and restart at login:

```bash
brew services start redis
```

### Ruby

I recommend you use [RVM](#rvm) instead of

```bash
brew install ruby
```

### RVM

Install GPG keys:
```bash
gpg2 --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3 7D2BAF1CF37B13E2069D6956105BD0E739499BDB
```

Install RVM with default Ruby:
```bash
\curl -sSL https://get.rvm.io | bash -s stable
```

### SASS

```bash
brew install sass/sass/sass
```

### Tailwind CSS

Tailwind CSS is a utility-first CSS framework that has become the dominant choice for styling modern web applications. It provides a comprehensive set of utility classes for rapid UI development.

```bash
npm install -g tailwindcss
# or with pnpm
pnpm install -g tailwindcss
```

Initialize Tailwind in your project:

```bash
npx tailwindcss init
```

Tailwind's utility-first approach eliminates the need to write custom CSS while maintaining flexibility and enabling rapid prototyping.

### PostCSS

PostCSS is a tool for transforming CSS with JavaScript plugins. It's essential for modern CSS workflows and is used by Tailwind CSS and many other tools.

```bash
npm install -g postcss postcss-cli
# or with pnpm
pnpm install -g postcss postcss-cli
```

PostCSS enables features like autoprefixing, nesting, and modern CSS transformations, making it a fundamental part of the modern frontend stack.

### Turborepo

Turborepo is a high-performance build system for JavaScript and TypeScript monorepos. It's become the go-to choice for managing multiple packages in a single repository.

```bash
npm install -g turbo
# or with pnpm
pnpm install -g turbo
```

Create a new Turborepo:

```bash
npx create-turbo@latest
```

Turborepo provides intelligent caching and parallel execution, making monorepo builds significantly faster than traditional approaches.

### Nx

Nx is a powerful build system with first-class monorepo support and integrated tooling. It's widely used for large-scale enterprise applications.

```bash
npm install -g nx
# or with pnpm
pnpm install -g nx
```

Create a new Nx workspace:

```bash
npx create-nx-workspace@latest
```

Nx provides advanced features like computation caching, distributed task execution, and smart rebuilds, making it ideal for large teams.

### Tmux

```bash
brew install reattach-to-user-namespace
brew install tmux
```

### Tmuxinator

```bash
brew install tmuxinator
```

### TOR

```bash
brew install tor
```

### PHP

```bash
brew install php
```

### Postman

```bash
brew install --cask postman
```

### Bruno

Bruno is a fast, open-source API client that stores collections directly in your filesystem. It's a privacy-focused alternative to Postman.

```bash
brew install --cask bruno
```

Bruno stores your API collections in plain text files (Bru format) making them easy to version control with Git. It's ideal for teams who want to track API changes alongside their code.

### SourceTree

*Personally I prefer to use the terminal but some developers prefer to use this type of tools*

```bash
brew install --cask sourcetree
```

### Vagrant

```bash
brew install --cask vagrant
```

#### Keep VirtualBox Guest Additions updated

```bash
vagrant plugin install vagrant-vbguest
```

### VirtualBox

```bash
brew install --cask virtualbox
```

### Visual Studio Code

```bash
brew install --cask visual-studio-code
```

### X11

```bash
brew install --cask xquartz
```

### Yarn

```bash
brew install yarn
```

### ZSH

```bash
brew install zsh
```

## 👨🏻‍🎨 Designer apps

### Figma

```bash
brew install --cask figma
```

### Sketch

```bash
brew install --cask sketch
```

You should also consider using:
- [Sketch Mirror](https://apps.apple.com/us/app/sketch-mirror/id677296955) (iOS app)
- [User Flows](https://abynim.github.io/UserFlows/) (plugin)
- [Craft](https://www.invisionapp.com/craft) (plugin)

Cost: $99

### InVision

```bash
brew install --cask invisionsync
```

## 🧰 Really useful apps

### Dropbox

Dropbox is a modern workspace designed to reduce busywork-so you can focus on the things that matter. Sign in and put your creative energy to work.


```bash
brew install --cask dropbpox
```

### Google Drive

Google's powerful search capabilities are embedded in Drive and offer unmatched speed, performance, and reliability. And features like Priority use AI to predict ...


```bash
brew install --cask google-drive
```

### Harvest

See where your time is going, improve your projects, increase efficiency. Schedule Future Projects. Easy, Intuitive Interface.

```bash
brew install --cask harvest
```

### Notion

Too many tools? Too much chaos? With Notion, all your work is in one place. All your projects tracked. All the features you need. Hassle-free wiki software. Better shared docs. Types: Personal Free, Personal Pro, Team, Enterprise.

```bash
brew install --cask notion
```

### PoEdit

```bash
brew install --cask poedit
```

### RectangleApp

Move and resize windows in macOS using keyboard shortcuts or snap areas

```bash
brew install --cask rectangle
```

### Signal

Instant messaging application focusing on security and privacy.

```bash
brew install --cask signal
```

### Slack

A better way to communicate. Unlike email, conversations in Slack are easy to follow. And they're more than conversations — you can make calls, share files, and even connect with other apps.

```bash
brew install --cask slack
```

### Spotify

Spotify is a digital music service that gives you access to millions of songs.


```bash
brew install --cask spotify
```

### Telegram

Telegram lets you access your chats from multiple devices. Fast. Telegram delivers messages faster than any other application.

```bash
brew install --cask telegram
```

### The-unarchiver

Unpacks archive files

```bash
brew install --cask the-unarchiver
```

### Transmission

Open-source BitTorrent client

```bash
brew install --cask transmission
```

### VLC

Multimedia player

```bash
brew install --cask vlc
```

### Zoom

*I recommend you look for an alternative to zoom* 🤷🏻‍♂️

Zoom is the leader in modern enterprise video communications, with an easy, reliable cloud platform for video and audio conferencing, chat, and webinars across mobile, desktop, and room systems.

```bash
brew install --cask zoomus
```


## 🗃️ Other stuff

### Update Everything easily

Once in a while, run the following command and everything you’ve installed with Homebrew will update automatically:

```bash
brew update && brew upgrade && brew cleanup && brew doctor
```

That one command is all you need to keep your system up to date. 🙌 I usually run it when I start a new project, but feel free to do so whenever you like.

(When you run this command, if Homebrew suggests additional commands for you to run, go ahead and run them. If a command begins with sudo and you are prompted for a password, use your Mac’s admin password.)

That’s it for the command line!

### Zsh prompt for Astronauts. 🤩

[Spaceship ZSH](https://denysdovhan.com/spaceship-prompt/) is a minimalistic, powerful and extremely customizable Zsh prompt. It combines everything you may need for convenient work, without unnecessary complications, like a real spaceship and I really love it.

![Spaceship prompt](https://user-images.githubusercontent.com/10276208/36086434-5de52ace-0ff2-11e8-8299-c67f9ab4e9bd.gif)

#### Requirements

To work correctly, you will first need:

- [zsh](#zsh) (v5.2 or recent) must be installed.
- Powerline Font must be installed and used in your terminal (for example, switch font to [Fira Code](#font-fira-code)).

#### Installing with oh-my-zsh

Clone this repo:

```bash
git clone https://github.com/denysdovhan/spaceship-prompt.git "$ZSH_CUSTOM/themes/spaceship-prompt" --depth=1
```

Symlink `spaceship.zsh-theme` to your oh-my-zsh custom themes directory:

```bash
ln -s "$ZSH_CUSTOM/themes/spaceship-prompt/spaceship.zsh-theme" "$ZSH_CUSTOM/themes/spaceship.zsh-theme"
```

Set `ZSH_THEME="spaceship"` in your `.zshrc`.

If you are looking for an alternative  [Starship](https://starship.rs/) is one of them.

### Our privacy matters

That is why I recommend using Firefox. Especially Firefox in the version 85 [cracks down on supercookies](https://blog.mozilla.org/security/2021/01/26/supercookie-protections/).

My list of extensions:

- [uBlock Origin](https://github.com/gorhill/uBlock#ublock-origin). An efficient blocker add-on for various browsers. Fast, potent, and lean. With uBlock I am subscribed to an [adblock list](https://github.com/hoshsadiq/adblock-nocoin-list) to block "browser-based crypto mining"
- [DuckDuckGo Privacy Essentials](https://duckduckgo.com/app). DuckDuckGo Privacy Essentials comes packed with best-in-class privacy essentials and makes browsing in Firefox even faster.
- [Facebook Container](https://github.com/mozilla/contain-facebook).  Facebook Container works by isolating your Facebook identity into a separate container that makes it harder for Facebook to track your visits to other websites with third-party cookies.

Another tool that I like it is [AdGuard](https://adguard.com). AdGuard is ta standalone ad blocker for Mac, Iphone, etc... No need for extra applications or browser extensions. Just download ad blocker for Mac by AdGuard and kill a small flock of birds with one stone. 🤷🏻‍♂️

## Conclusion

You're all set! 🎉

That’s all our need to get up and running with JavaScript-based front-end development on our Mac.

### Credits

- [Set up your shiny OS X for software development](https://github.com/danguita/osx-for-developers)
- [How to Set Up a Mac for Web Development](https://michaeluloth.com/how-to-set-up-a-mac-for-web-development)
- [Front-End Development Setup on a Mac](https://github.com/asuh/front-end-macos)
- [Setup your Mac for development, 2020 edition](https://dev.to/v3frankie/setup-your-mac-for-development-2020-edition-1c8a)
- [My list of essential tools and apps for design & front-end development](https://blog.prototypr.io/my-list-of-essential-tools-and-apps-for-design-front-end-development-9e5fd02b3d07)
- [How to Set Up Your MacBook for Web Development in 2020](https://medium.com/better-programming/setting-up-your-mac-for-web-development-in-2020-659f5588b883)
