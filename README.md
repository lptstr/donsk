# donsk
donsk is a minimalistic static-site generator built for those who are tired of the complexity of other site generators like Hugo or Jekyll.

## Features
- **Simplicity** - in donsk, there are no themes to configure - just the default, minimalist theme. There are also about two configuration value - just two. Very little can go wond there.
- **Fast** - donsk is also fast. Blazingly fast. Maybe not as fast as it could have been had it been written in C or Rust, but it is still pretty fast. It is, after all, less than 100 lines of bash code.
- **Hackable** - because donsk is just a few bash scripts, it is very easy to tweak or customize donsk to whatever you like.

## Installation
### \*nix systems
Install the following dependencies:
- bash 3+
- pandoc
- imagemagick
- jpegoptim
- pngquant
- img2webp

Then, fork this repository and clone it locally. Now you can skip to the 'Getting Started' section.

### Windows (experimental)
First, download and install MSYS2.
E.g. with [Scoop](https://scoop.sh):
```
$ scoop install msys2
```
Then, launch msys2 and run the following code:
```
$ sudo pacman -S pandoc imagemagick
```
Then install `yay` if you haven't already:
```
$ git clone https://aur.archlinux.org/yay.git
$ cd yay
$ makepkg -si
```
Then install the rest of the dependencies:
```
$ yay -S jpegoptim pngquant img2webp
```
Fork this repository and clone it locally.
