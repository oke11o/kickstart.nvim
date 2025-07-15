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

## Buffer Management (barbar.nvim)

### Buffer Navigation
- `Ctrl-,` - Move to previous buffer
- `Ctrl-.` - Move to next buffer
- `Alt-1` through `Alt-9` - Jump to specific buffer by number
- `Alt-0` - Jump to last buffer

### Buffer Operations
- `Ctrl-c` - Close current buffer
- `Ctrl-b` - Close all buffers except current
- `Alt-p` - Pin/unpin buffer
- `Alt-<` - Move buffer left
- `Alt->` - Move buffer right