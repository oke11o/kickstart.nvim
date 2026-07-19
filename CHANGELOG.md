# Changelog

All notable changes to this Neovim configuration will be documented in this file.

## [2026-07-19]

### Changed

- Rebased personal `sab` branch onto latest upstream `kickstart.nvim` (74 upstream commits).
- Upstream migrated the plugin manager from **lazy.nvim → vim.pack**; re-implemented all personal customizations on top of the new upstream `init.lua`:
  - `nvim-tree` and `auto-save.nvim` re-declared as `vim.pack` specs.
  - `conform.nvim` config ported (format on `BufLeave`, full `formatters_by_ft`).
  - LSP servers `gopls`, `pyright`, `ts_ls` enabled; Mason formatter tools added.
  - Personal options (leader `;`, relativenumber, per-filetype indent, `ttimeoutlen`), keymaps (buffer nav, copy-path, registers, comment toggle, `;a` tree toggle, `;sF`/`;sG` smart search) and `tokyonight-day` colorscheme re-applied.

### Removed

- Dropped `[d`/`]d` diagnostic remaps — now covered by Neovim 0.12 built-in defaults.

## [2026-01-06]

### Added

- `;r` - show all registers
- `;ya`, `;yb`, `;yc` - yank to named registers a/b/c (normal + visual)
- `;pa`, `;pb`, `;pc` - paste from named registers a/b/c
- `;p` (visual mode) - paste without overwriting register
