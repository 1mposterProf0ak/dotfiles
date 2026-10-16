# Dotfiles

These are the dotfiles that I currently use on Debian, however they presumably should work on Arch, RHEL, FreeBSD, or any other UNIX-like OS that uses the same software.

These files were preserved using [chezmoi](https://www.chezmoi.io/) and are designed to be quickly deployed on new machines using the same tool.

## Installation

### Dependencies

* wget
* curl
* vim
* git

### Install

Arch:

```bash
pacman -S chezmoi
```

FreeBSD:

```sh
pkg install chezmoi
```

Debian: just [install from a pre-built package and verify the files](https://www.chezmoi.io/install/#download-a-pre-built-package).

## Usage

### Restoration/Deployment

On a new machine with `chezmoi` installed, execute the following:

```bash
chezmoi init --apply 1mposterProf0ak
```

> [!NOTE]
> This will simply restore the dotfiles and not enable write access to the repo. You'll have to us ssh and have my private key and hardware auth token to do that ;)

### Adding new files

```bash
chezmoi add ~/.bashrc
chezmoi cd
git pull
git add .
git commit -m "message"
git push
```

### Editing dotfiles already in the repo

```bash
chezmoi edit ~/.bashrc
chezmoi diff
```

#### Applying changes to actual dotfiles from chezmoi repo

```bash
chezmoi -v apply
```
