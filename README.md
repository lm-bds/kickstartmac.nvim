# kickstartmac.nvim

My readable, single-file Neovim configuration for macOS, based on [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim).

This is a personal configuration rather than a Neovim distribution. The main configuration remains in `init.lua` so the complete startup path can be read and changed without learning a custom framework first.

## Included tooling

- `lazy.nvim` plugin management
- Telescope search and navigation
- Treesitter syntax parsing
- LSP configuration, completion, formatting and diagnostics
- Git signs, automatic pairing, indentation guides and linting
- Sensible macOS clipboard integration through `unnamedplus`

## Requirements

- Neovim 0.10 or newer
- Git
- A C compiler for Treesitter parsers
- `make`, `unzip` and a supported terminal
- Optional: a Nerd Font for icons

On macOS with Homebrew:

```bash
brew install neovim git ripgrep fd
```

## Install

Back up any existing configuration, then clone this repository:

```bash
mv ~/.config/nvim ~/.config/nvim.backup 2>/dev/null || true
git clone https://github.com/lm-bds/kickstartmac.nvim.git ~/.config/nvim
nvim
```

The first launch bootstraps `lazy.nvim` and installs the configured plugins. Run `:checkhealth` after installation to identify missing language-specific tools.

## Update and validate

Inside Neovim:

```text
:Lazy update
:checkhealth
```

Lua formatting is checked with StyLua:

```bash
stylua --check .
```

## Customisation

- Change general settings and core plugins in `init.lua`.
- Add personal plugins in `lua/custom/plugins/init.lua` or another module under `lua/custom/plugins/`.
- Set `vim.g.have_nerd_font = true` in `init.lua` if the terminal uses a Nerd Font.

For the teaching-oriented upstream documentation, see [nvim-lua/kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim).

## Licence

MIT. This fork retains the upstream licence and attribution.
