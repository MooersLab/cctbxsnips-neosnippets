# cctbxsnips-neosnippets

![Version](https://img.shields.io/static/v1?label=cctbxsnips-neosnippets&message=0.1&color=brightcolor)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)



## CCTBX

[CCTBX](https://github.com/cctbx/cctbx_project) is the Computational Crystallography Toolbox. 
Its development is based at Lawrence-Berkeley National Laboratory.
It provides code for computations with diffraction data and atomic coordinates of proteins and small molecules.
It has C++ and Python ports.
It is available in Anaconda in the conda-forge channel as cctbx-base for python3.8 through 3.11 for Windows, macOS, and Linux.

### Blaine's cctbx install protocol

I assume that Anaconda has already been installed. We also create the Jupyter Notebook kernel while we are at it. Execute one line at a time: Wait for the execution to finish before executing the next line.

```bash
conda create --name cctbx39 python=3.9
conda activate cctbx39
conda install -c conda-forge cctbx-base -y
conda install ipykernel -y
python -m ipykernel install --user --name cctbx39 --display-name "cctbx python3.9"
```

The second to last command triggers the installation of Jupyter in the cctbx39 env.
The last command creates and installs the Jupyter kernel in `~/Library/Jupyter/kernels/cctbx39` on the Mac.
Select **cctbx python3.9** from the list of kernels when opening a new notebook in Jupyter.

Replace the *3.9* or *39* above with whatever version of Python you want to use (between 3.8 and 3.11).

## Neosnippets

[Neosnippets](https://github.com/Shougo/neosnippet.vim) is a popular snippet manager for Vim.
It also works with Neovim.
Its development has plateaued.

There are other snippets managers for Vim and NeoVim, such as `ultisnip`s and `snipmate`.
To complicate matters more, there several alternate systems for managing plugins.


## The problems that this repo addresses

1. **Facilitate code reuse**. The use of code snippets can save time by reusing existing code.
The presence of tab stops in code snippets can help ensure that all parameters that need to be customized for a new problem are considered.
Thus, tab stops can reduce subsequent debugging.

3. **Use of Emacs to edit Jupyter and Colab code and markdown cells** The existing snippet formats for Jupyter and Colab notebooks do not support tab triggers and tab stops: These are standard features of code snippet systems in most text editors.
We can overcome these limitations by sending the active code cell to Vim or NeoVim via the GhostText extension for the browser and the ghosttext.vim plugin.

## Installation

1. Install the snippets for Vim.

I assume that the `neosnippets` plugin has already been properly installed.
The snippets are stored in a single file called `cctbx.snips`.
I store this file in a folder called `~/.vim/my-snippets/neosnippets`.
You may have to concatenate the `cctbx.snips` with an existing `python.snippets` file.

```bash
cd ~/.vim/my-snippets/neosnippets
git clone https://github.com/MooersLab/cctbxsnips-neosnippets.git
cd cctbxsnips-neosnippets/
mv cctbx.snips ../.
cd ..
rm -rf cctbxsnips-neosnippets
```

2. **Optional** If you want to use these snippets from Vim or NeoVim to edit live cells in Jupyter or Colab notebooks, install [GhostText](https://ghosttext.fregante.com/) in your browser and the [Vim Ghost](https://github.com/raghur/vim-ghost)plugin for Vim.
3. Install the [nvim-ghost](https://github.com/subnut/nvim-ghost.nvim] plugin for NeoVim).

## Related repositories
- [cctbxsnips-Emacs](https://github.com/MooersLab/cctbxsnips-Emacs) CCTBX snippets for the yasnippet snippet system in for Emacs.
- [cctbxsnips-SublimeText3](https://github.com/MooersLab/cctbxsnips-SublimeText3) CCTBX snippets for Sublime Text 3 (ST3).
- [cctbxsnips-VSC](https://github.com/MooersLab/cctbxsnips-VSC) CCTBX snippets for Visual Studio Code (VSC).
- [cctbxsnips-UltiSnips](https://github.com/MooersLab/cctbxsnips-Ultisnips) CCTBX snippets for Vim or NeoVim via UltiSnips plugin.
- [cctbxsnips-Snipmate](https://github.com/MooersLab/cctbxsnips-snipmate) CCTBX snippets for Vim or NeoVim via snipmate plugin.
- [cctbxsnips-Atom](https://github.com/MooersLab/cctbxsnips-Atom) CCTBX snippets for Atom.
- [Jupyterlab cctbx snippets](https://github.com/MooersLab/jupyterlabcctbxsnips) CCTBX snippets for JupyterLab with the `jupyterlab-snippets` extension or the jupyterlab-snippets-mutlimenus extension.
- [Jupyterlab cctbx plus snippets](https://github.com/MooersLab/jupyterlabcctbxsnipsplus) The variant of the `jupyterlabcctbxsnips` library with comments to guide editing of the snippets.
- [Colab cctbx snippets](https://github.com/MooersLab/colabcctbxsnips) Colab snippets.
