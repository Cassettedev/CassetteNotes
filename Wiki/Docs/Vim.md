[[Home]]
[[Cassette]]
[[Wiki]]
[[Blog]]

[[Humanities]]
[[STEM]]
[[Health]]
[[Docs]]

### Installing plugins with VimPlug
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
Remove it from the .vimrc file and;
`:PlugClean`

