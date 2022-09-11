# Vim is a text editor
To enter a file with vim, simply type:
```
vim filename.fileextension
```
while inside the same directory as the file.

## Essential keybings
The navigation keys are:
`h j k l` for left down up right. `i` to enter inset mode, and `a` to enter insert mode onto the next letter. use `esc` to exit insert mode. While in normal mode, enter `crtl+v` to enter Visual mode.   

## Hybrid/Relative line numbers
To set hybrid/relative line numbers, use this:
```
set number relativenumber
set nu rnu
```

### Installing plugins with VimPlug
```
curl -fLo ~/.vim/autoload/plug.vim --create-dirs https://raw.githubusercontent.com/junegunn/vim-plug/master/plug.vim`
```
installs vimplug
Use(in .vimrc):
```
call plug#begin('~/vim/plug')

call plug#end()
```
to initiate the plugin calls.

As an example, use:
```
call plug#begin('~/vim/plug')

Plug 'kblin/vim-fountain'

call plug#begin('~/vim/plug')
```
to call a plugin

I keep my plugins in my ~/.vim/plug directory

in the .vimrc file where the plugins are called, enter:
`:PlugInstall` to install any plugins.
To update VimPlug:
`:PlugUpgrade`
To update a plugin:
`:PlugUpdate[PLUGIN NAME]`
To update all plugins:
`:PlugUpdate`
To uninstall a plugin:
Remove it from the .vimrc file and type:
`:PlugClean`


