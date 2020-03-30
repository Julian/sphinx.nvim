# sphinx.nvim

![CI](https://github.com/stsewd/sphinx.nvim/workflows/CI/badge.svg)

[Sphinx](https://www.sphinx-doc.org/) integrations for Neovim.

**This plugin is still under development, some functionalities may change.**

# Available integrations

## [coc.nvim](https://github.com/neoclide/coc.nvim/)

![01](https://user-images.githubusercontent.com/4975310/77864888-f41f4080-71f0-11ea-9108-741df3cbf1ce.png)
![02](https://user-images.githubusercontent.com/4975310/77864900-fed9d580-71f0-11ea-8e5e-60c8df1c06e9.png)

Source for [cross-referencing roles](https://www.sphinx-doc.org/en/master/usage/restructuredtext/roles.html#cross-referencing-syntax),
i.e `:ref:`, `:doc:`, `py:func`, etc.

**Note:** this plugin makes use of the inventory file from Sphinx,
so you need to have built your docs at least once to get suggestions,
and rebuild when your docs change to get the up to date suggestions.
You can use [sphinx-autobuild](https://github.com/GaretJax/sphinx-autobuild) to rebuild your docs automatically when there is a change.

# Coming soon

- Support for Intersphinx
- Integration with [fzf](https://github.com/junegunn/fzf/)

# Installation

Install using [vim-plug](https://github.com/junegunn/vim-plug).
Put this in your `init.vim`.

```vim
Plug 'stsewd/sphinx.nvim', { 'do': ':UpdateRemotePlugins' }
```

**Note:** you need to have `coc.nvim` installed to use the `coc.nvim` integration.
See <https://github.com/neoclide/coc.nvim/#quick-start>.

# Configuration

Default values are shown in the code blocks.

## g:sphinx_output_dirs

Where to search for the local inventory file (`objects.inv`).
The directories are relativa to the `conf.py` file.

```vim
let g:sphinx_output_dirs = ['_build/html', 'build/html', '../_build/html', '../build/html']
```

## g:sphinx_local_only

Fetch all inventory files from intersphinx or just the local inventory file.

```vim
let g:sphinx_local_only = 0
```
