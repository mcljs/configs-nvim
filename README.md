# Vim for JavaScript/React/Angular development (Linux and MAC Setup)

## 1. Install `vim-plug` as a plugin manager

`vim-plug` advantages:
- installs each plugin in its own directory
- includes commands for plugin installation/update/removal: [See the list of commands here](https://github.com/junegunn/vim-plug)
- parallel installation/update of plugins
- faster than `Vundle`

`vim-plug` installation:

* Run this command in terminal
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs \
    https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim
```
* Create the `.vimrc` file in your local dir, if there's none yet

```
touch ~/.vimrc
```

* Open the `.vimrc` file and paste:

```
" Specify a directory for plugins
" - For Neovim: ~/.local/share/nvim/plugged
" - Avoid using standard Vim directory names like 'plugin'
call plug#begin('~/.vim/plugged')

" List here the plugins with Plug commands
" Shorthand notations can be used, as well as any valid GIT URLs
" Make sure you use single quotes
" See all possible ways to list a plugin: https://github.com/junegunn/vim-plug
" Ex: Plug 'https://github.com/username/reponame.git'

" Initialize the plugin system
call plug#end()
```

## 2. Install typescript

```
npm install -g typescript
```

## 3. Install `typescript-vim` plugin to enable typescript syntax support

* Open `~/.vim/plugins.vim` file
* Add `Plug 'https://github.com/leafgarland/typescript-vim'` before `call plug#end()`
* Also add the following lines after `call plug#end()` to enable the plugin to display compilation errors in the QuickFix window:

```
let g:typescript_compiler_binary = 'tsc'
let g:typescript_compiler_options = ''
autocmd QuickFixCmdPost [^l]* nested cwindow
autocmd QuickFixCmdPost    l* nested lwindow
```

* Open vim and type `:PlugInstall`
* Open a `.ts` file with vim: `vim someFile.ts`
* Run `:make` while editing a TypeScript file to execute the `tsc` compiler and display errors in the QuickFix window:


## 5. Install `vim-javascript` plugin to enable javascript syntax highlighting

* Open `~/.vim/plugins.vim` file
* Add `Plug https://github.com/pangloss/vim-javascript`
* Open vim and type `:PlugInstall`
