# donsk
donsk is a minimalistic static-site generator built for those who are tired of the complexity of other site generators like Hugo or Jekyll.

See [this website](https://kiedtl.surge.sh) for a demo.

## Features
- **Simplicity** - in donsk, there are no themes to configure - just the default, minimalist theme. There are also only about two configuration values that you really need to edit. If you want further customization, there are a few more.
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

## Getting Started
First, edit the `src/_content/index.md` file and add whatever content you want. The file can contain both markdown and HTML content. All your web pages will go into the `src/_content` folder.

Now you can add any other webpages you want as `.md` files. You can create folders as you wish and add content into them. Add your miscellaeneous files into the `src/_content/_files/` directory, and your images into the `src/_content/_images/` directory. The files will be copied **as is** into the root directory of you site, and the images will be optimized and copied into an `images/` folder in the root directory of your website.

Next, edit the `config` file. Edit the variables at the top of the file, and change it to the appropriate value. Change the value of `site_name` to the name of your site, and add all your content folders to the `folders` variable. For example, if you created a `snowy.md` file in a `kittens/` folder in `src/_content/`, you must add it like so:
```bash
folders=("folder1" "folder2" "kittens")
```
**Note**: All content folders must be added for donsk to generate any content contained in the folders. If the folders are not explicitly listed, donsk will ignore those folders.

Now, run `mksite`:
```bash
~/website/donsk/src/$ ./mksite
```
and donsk will generate your site and add it to `src/_website`. Now you can upload this content to whatever hosting provider you prefer, like [Surge](https://surge.sh):
```
$ cd _website
$ surge --domain mydomain.surge.sh
```

## Blogging
Blogging with donsk may not be as easy as with Wordpress, but it still isn't as complicated as other static-site generators like Hexo or Hugo.
To create a new post, `cd` to the `src/_content/_posts/` directory, and create a new file called `001-my-post-title.md`. Add you content into this file, and when you are done, you will have to update the `src/_content/_posts/index.md` file to list the new blog post.

## Update
To update the mksite script, just run the `update` script once. **Beware**: This will overwrite all changes made to the mksite script.

## Inspiration
- [blag](https://github.com/dylanaraps/blag) by **@dylanaraps**

## License
This project is licensed under the GNU Affero General Public License v3.0 (AGPL-v3.0).
