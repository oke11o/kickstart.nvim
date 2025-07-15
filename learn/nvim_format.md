# Neovim Formatting Configuration

## Current Setup

- **Auto-format on save**: DISABLED (to avoid undo issues)
- **Auto-format on buffer leave**: ENABLED (when switching to another file/window)
- **Manual formatting**: Available via hotkeys

## Formatting Hotkeys

- `;f` - Format current buffer (works in all modes)

## Why This Configuration?

This setup avoids the common problem where auto-formatting on save interferes with undo operations. Instead of formatting on every save, formatting happens:

1. When you leave the buffer (switch to another file)
2. When you manually trigger it with hotkeys

This allows you to:

- Use `u` (undo) without formatting getting in the way
- Have clean code when switching between files
- Manually format whenever needed

## Formatters by Language

- **Lua**: stylua
- **Go**: gofumpt, goimports
- **Python**: isort, black
- **JavaScript/TypeScript**: prettierd, prettier
- **HTML/CSS/SCSS**: prettierd, prettier
- **JSON/YAML/Markdown**: prettierd, prettier
- **Rust**: rustfmt
- **C/C++**: clang-format
- **Java**: google-java-format
- **PHP**: php_cs_fixer
- **Shell scripts**: shfmt

## Commands

- `:ConformInfo` - Show information about conform.nvim setup and active formatters

## Configuration Location in init.lua

The formatting configuration is located in the `conform.nvim` plugin setup, approximately at **line 1012-1077**:

```lua
{ -- Autoformat
  'stevearc/conform.nvim',
  ...
  config = function()
    local conform = require('conform')

    conform.setup({
      format_on_save = false,  -- Disabled to avoid undo issues
      formatters_by_ft = { ... }
    })

    -- Format on buffer leave (line ~1067)
    vim.api.nvim_create_autocmd("BufLeave", {
      pattern = "*",
      callback = function()
        if vim.bo.buflisted and vim.bo.modifiable then
          conform.format({ async = false, lsp_format = 'fallback' })
        end
      end,
    })
  end,
}
```

Key configuration points:

- **Hotkeys definition**: lines 1016-1033
- **Format on save disabled**: line 1040
- **Formatters by language**: lines 1043-1063
- **Auto-format on buffer leave autocmd**: lines 1067-1075 (inside the conform.nvim config function)
  - This is where the `BufLeave` autocmd is created
  - It runs `conform.format()` when you switch away from a buffer
  - Located within the `config = function()` block of the conform.nvim plugin setup
