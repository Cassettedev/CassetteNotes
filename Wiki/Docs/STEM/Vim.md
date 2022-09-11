# Vim is a text editor
To enter a file with vim, simply type:
```
vim filename.fileextension
```
while inside the same directory as the file.

## Essential keybings
The navigation keys are:
`h j k l` for left down up right. `i` to enter Inset Mode, and `a` to enter Insert Mode onto the next letter. use `esc` to exit Insert Mode.
If you want to move several lines/collums, use a number before pressing `h j k l`, like `3+k` to go up 3 lines.
If you want to go to the bottom of the file, press `Shift+g`, and `g+g` to go to the top. You can use `3+g` to go to line number 3, replace 3 with any number (does not work well with relative numbers).
When on a line with another line below it, press `o` to open a new line inbetween the lines. This will put you in insert mode automatically.
To move between open lines of code like the one created above, press `Shift+[` to move between them, using `[` or `]` for up and down.
To move foward to the next word, press `w`, and `b` to move back a word.
Type `0` to move the beginning of a line. Type `Shift+^` to move to the beginning of the text on the line.
To delete and change the words within a bounding set of characters, ie "" or (), type `d+i+(` or whatever bounding characters you want.
Type `u` to undo a change, type `crtl+r` to redo.
You can delete a word with `d+w`, delete the current line with `d+d`, delete x number of lines with `3+d+d` with 3 lines as an example, `d+w` to delete next word, `d+b` to delete previous word, `d+i+p` to delete inner paragraph. You can delete a single character with `x`.
You can use `c+i+w` to delete the inner word and go to insert mode, `c+i+p` to change inner paragraph, `c+i+{` to change anything between curly braces.
You can change the word under your cursor with `i`, so `i+t` to change a letter to a t.
You can press `Shift+`` to toggle the casing under a letter.
Use `:q` to quit, `:q!` to quit without saving, `:wq` to save and quit, `:w` to save.
While in normal mode, enter `crtl+v` to enter Visual Mode, and `shift+v` to enter bigger Visual Mode.
Use `Shift+$` to go to the end of the line you're on.


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


