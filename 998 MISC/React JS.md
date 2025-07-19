### VS Code configuration
1. Install the following extensions: Prettier, Vim, File Bunny
2. Type `Ctrl + Shift + p` to open the command drop down menu
3. Type `User Settings (JSON)`
4. Add the following lines:
```json
// ...
    "vim.vimrc.enable":true,
    "vim.vimrc.path": "~/.config/nvim/init.vim",
    "vim.useSystemClipboard": true,
    "vim.handleKeys": {
        "<C-w>": false
    },
    // "vim.insertModeKeyBindings": [
    //     {
    //       "before": ["d", "f"],
    //       "after": ["<Esc>"]
    //     }
    //   ],
    // "vim.normalModeKeyBindingsNonRecursive": [
    //     // switch b/w buffers
    //     {"before": ["<Alt-h"], "commands": [":bprevious"]},
    //     {"before": ["<Alt-l"], "commands": [":bnext"]},

    //     // splits
    //     {"before": ["<Space-v"], "commands": [":vsplit"]},
    //     {"before": ["<Space-s"], "commands": [":split"]},
    // ],
    "editor.lineNumbers": "relative",
    "editor.fontFamily": "'JetBrainsMono Nerd Font','Droid Sans Mono', 'monospace', monospace",
    "editor.formatOnSave": true,
    "editor.minimap.enabled": false
// ...
```
5. Type on the command drop down menu `Open Keyboard Shortcuts (JSON)`
6. Add the following lines:
```json
[
// ...
    {
        "key": "alt+l",
        "command": "workbench.action.nextEditor"
    },
    {
        "key": "alt+h",
        "command": "workbench.action.previousEditor"
    },

    {
        "key": "ctrl+shift+p",
        "command": "workbench.action.showCommands",
        "when": "!inQuickOpen"
    },
    {
        "key": "ctrl+shift+p",
        "command": "workbench.action.closeQuickOpen",
        "when": "inQuickOpen"
    },

    {
        "key": "ctrl+p",
        "command": "workbench.action.quickOpen",
        "when": "!inQuickOpen"
    },
    {
        "key": "ctrl+p",
        "command": "workbench.action.closeQuickOpen",
        "when": "inQuickOpen"
    }
// ...
]
```

### Create a React JS app
npm create vite@latest
