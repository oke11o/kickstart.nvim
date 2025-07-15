# nvim-tree Commands and Operations

## File and Directory Operations

### Moving Files
1. Navigate to the file you want to move
2. Press `x` - cut the file
3. Navigate to the target directory
4. Press `p` - paste the file

### Basic File Operations
- `a` - Add/create new file or directory
  - Enter filename to create a file
  - End with `/` to create a directory (e.g., `newfolder/`)
  - Can create nested paths: `folder/subfolder/file.txt`
- `d` - Delete file/directory
- `r` - Rename file/directory
- `x` - Cut file/directory
- `c` - Copy file/directory
- `p` - Paste file/directory

### Navigation and Display
- `H` - Toggle hidden files visibility
- `I` - Toggle git ignored files visibility
- `g?` - Show help with all available commands
- `:NvimTreeFindFile` - Find and focus current file in tree

### Tree Toggle
- `;a` - Toggle nvim-tree (show/hide)
- `:NvimTreeToggle` - Toggle tree visibility
- `:NvimTreeOpen` - Open tree
- `:NvimTreeClose` - Close tree
- `:NvimTreeFocus` - Move focus to tree

## Configuration Notes
- Auto-focus on current file is enabled
- Shows hidden files and .gitignore files by default
- Only `.git` directory is hidden