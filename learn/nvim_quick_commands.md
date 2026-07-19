# Neovim Quick Commands

## nvim-tree Toggle and Navigation

### Show/Hide Tree
- `;a` - Toggle nvim-tree (show/hide)
- `:NvimTreeToggle` - Toggle tree visibility
- `:NvimTreeOpen` - Open tree
- `:NvimTreeClose` - Close tree
- `:NvimTreeFocus` - Move focus to tree

## nvim-tree File Operations

### Creating Files and Directories
- `a` - Add/create new file or directory
  - Enter filename to create a file
  - End with `/` to create a directory (e.g., `newfolder/`)
  - Can create nested paths: `folder/subfolder/file.txt`

### Other File Operations
- `d` - Delete file/directory
- `r` - Rename file/directory
- `x` - Cut file/directory
- `c` - Copy file/directory
- `p` - Paste file/directory
- `?` - Show all available commands and keybindings

### Navigation
- `H` - Toggle hidden files visibility
- `I` - Toggle git ignored files visibility

## Buffer Management (Standard Vim)

### Buffer Navigation
- `Tab` - Next buffer (recommended)
- `Shift+Tab` - Previous buffer (recommended)  
- `Ctrl-,` - Previous buffer (if working)
- `Ctrl-.` - Next buffer (if working)
- `;bp` - Previous buffer (leader key)
- `;bn` - Next buffer (leader key)
- `;bl` - List all buffers
- `:b<number>` - Jump to buffer by number
- `:b<partial_name>` - Jump to buffer by partial name

### Buffer Operations
- `Ctrl-c` - Close current buffer
- `;bd` - Close current buffer (alternative)
- `:bd` - Close current buffer (command)
- `:bdelete` - Close current buffer (full command)
- `:ls` - List all buffers (same as `;bl`)