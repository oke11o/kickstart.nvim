# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is a kickstart.nvim-based Neovim configuration that serves as a personal development environment setup. It's built on the philosophy of being a single-file, completely documented starting point rather than a distribution.

## Key Configuration Details

### Architecture
- **Single-file approach**: Primary configuration in `init.lua` (1,167 lines) with extensive inline documentation
- **Leader key**: `;` (semicolon) used for both leader and maplocalleader
- **Plugin management**: Uses lazy.nvim with version locking via `lazy-lock.json`
- **Customization pattern**: User plugins go in `lua/custom/plugins/init.lua`, optional kickstart plugins can be uncommented in main init.lua

### Core Components

**File Management & Navigation**
- nvim-tree.lua configured as primary file explorer (not neo-tree)
- Telescope for fuzzy finding with comprehensive keymaps
- Auto-save enabled on text changes and insert leave

**Development Environment**
- LSP setup with mason.nvim for automatic server installation
- blink.cmp for modern completion (replaces nvim-cmp)
- conform.nvim for code formatting
- Currently configured for Lua development (lua_ls server)

**UI & Experience**
- tokyonight-day colorscheme
- barbar.nvim for buffer/tab management with extensive keymaps
- mini.nvim modules (statusline, surround, textobjects)
- Nerd Font support disabled by default (`vim.g.have_nerd_font = false`)

### Essential Keymaps

**File Operations**
- `;a` - Toggle nvim-tree file explorer
- `;sf` - Search files with Telescope
- `;sg` - Live grep search
- `;sn` - Search Neovim config files

**Buffer Management**
- `Ctrl-,` / `Ctrl-.` - Navigate between buffers
- `Ctrl-c` - Close current buffer
- `Ctrl-b` - Close all buffers except current
- `Alt-1` through `Alt-9` - Jump to specific buffer

**LSP Operations**
- `grd` - Go to definition
- `grr` - Find references
- `grn` - Rename symbol
- `gra` - Code action

### Development Workflow

**Plugin Management**
```bash
# View plugin status
nvim +Lazy

# Update plugins
nvim +"Lazy update"

# Plugin installation is automatic on startup
```

**Health Checking**
```bash
# Check overall Neovim health
nvim +checkhealth

# Check kickstart-specific health
nvim +"checkhealth kickstart"
```

**Configuration Management**
- All primary configuration in single `init.lua` file
- Custom plugins added to `lua/custom/plugins/init.lua` 
- Optional kickstart plugins can be enabled by uncommenting lines in init.lua
- Version control includes `lazy-lock.json` for reproducible plugin versions

### External Dependencies

**Required**
- Neovim 0.10+ (latest stable or nightly)
- git, make, unzip, C compiler (gcc)
- ripgrep (for telescope live grep)

**Optional**
- fd-find (for faster file finding)
- Nerd Font (set `vim.g.have_nerd_font = true` if available)
- Language-specific tools (npm for TypeScript, go for Golang, etc.)

### Customization Patterns

**Adding New Plugins**
Add to `lua/custom/plugins/init.lua`:
```lua
return {
  {
    'plugin-author/plugin-name',
    opts = {},
    config = function()
      -- setup code
    end,
  },
}
```

**LSP Configuration**
Add language servers to the `servers` table in init.lua around line 820:
```lua
local servers = {
  -- Add new servers here
  ts_ls = {},  -- TypeScript
  pyright = {},  -- Python
}
```

**Keymap Additions**
Follow the existing pattern with descriptive names:
```lua
vim.keymap.set('n', '<leader>key', function_or_command, { desc = '[D]escription' })
```

This configuration prioritizes educational value and readability over modularity, making it ideal for understanding and incrementally customizing Neovim behavior.